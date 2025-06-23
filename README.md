# InventoryHub - Full Stack Inventory Management System

A modern, full-stack inventory management application built with ASP.NET Core 9 Minimal API and Blazor WebAssembly. This project demonstrates the power of Microsoft's modern web development stack with AI-assisted development using Microsoft Copilot.

## 🎯 Project Overview

InventoryHub is a comprehensive inventory management solution that showcases modern full-stack development practices. Built as a learning project, it demonstrates the integration between a .NET 9 Minimal API backend and a Blazor WebAssembly frontend, with AI-assisted development using Microsoft Copilot.

## ✨ Features

### 🔧 Backend (ServerApp)
- **ASP.NET Core 9 Minimal API** - High-performance, lightweight API
- **CORS Configuration** - Cross-origin resource sharing for frontend integration
- **Product Management** - CRUD operations for inventory items
- **Category System** - Nested category information for products
- **JSON Serialization** - Structured API responses with nested objects
- **OpenAPI Support** - Built-in API documentation

### 🎨 Frontend (ClientApp)
- **Blazor WebAssembly** - Modern single-page application framework
- **Responsive Design** - Bootstrap-based responsive layout
- **Product Display** - Dynamic product listing with category information
- **Error Handling** - Comprehensive error management and user feedback
- **Loading States** - User-friendly loading indicators
- **HTTP Client Integration** - Seamless API communication

### 🤖 AI-Assisted Development
- **Microsoft Copilot Integration** - AI-powered development assistance
- **Code Generation** - Automated scaffolding of API endpoints
- **Debugging Support** - AI-assisted problem-solving
- **Performance Optimization** - AI-suggested caching and optimization strategies

## 🛠️ Technologies Used

### Backend Stack
- **ASP.NET Core 9.0** - Modern, cross-platform web framework
- **C# 12** - Latest C# language features
- **Minimal API** - Lightweight, high-performance API design
- **JSON Serialization** - System.Text.Json for data serialization

### Frontend Stack
- **Blazor WebAssembly** - C#-based single-page application framework
- **Bootstrap 5** - Responsive CSS framework
- **HTTP Client** - Built-in HTTP communication
- **Razor Components** - Component-based UI architecture

### Development Tools
- **Microsoft Copilot** - AI-assisted development
- **Visual Studio 2022** - Integrated development environment
- **Git** - Version control system
- **CORS Middleware** - Cross-origin resource sharing

## 🚀 Getting Started

### Prerequisites
- **.NET 9.0 SDK** or higher
- **Visual Studio 2022** or **Visual Studio Code**
- **Microsoft Copilot** (optional, for AI assistance)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/SametDulger/InventoryHub.git
   cd InventoryHub
   ```

2. **Restore dependencies**
   ```bash
   dotnet restore
   ```

3. **Run the backend server**
   ```bash
   cd ServerApp
   dotnet run
   ```

4. **Run the frontend client** (in a new terminal)
   ```bash
   cd ClientApp
   dotnet run
   ```

5. **Access the application**
   - **Backend API**: `https://localhost:7001` or `http://localhost:5001`
   - **Frontend App**: `https://localhost:7000` or `http://localhost:5000`

### Available Commands

- `dotnet run` - Start the development server
- `dotnet build` - Build the project
- `dotnet test` - Run unit tests (if available)
- `dotnet publish` - Publish for production

## 📁 Project Structure

```
InventoryHub/
├── FullStackSolution.sln          # Visual Studio solution file
├── ServerApp/                     # Backend API project
│   ├── Models/
│   │   └── Product.cs             # Product data model
│   ├── Program.cs                 # API entry point and configuration
│   ├── ServerApp.csproj           # Backend project configuration
│   ├── appsettings.json          # Application settings
│   └── ServerApp.http            # API test file
├── ClientApp/                     # Frontend Blazor app
│   ├── Pages/
│   │   ├── FetchProducts.razor    # Product listing page
│   │   ├── Home.razor            # Home page
│   │   ├── Counter.razor         # Sample counter page
│   │   └── Weather.razor         # Sample weather page
│   ├── Layout/                   # Application layout components
│   ├── wwwroot/                  # Static assets
│   ├── Program.cs                # Frontend entry point
│   ├── App.razor                 # Root application component
│   └── ClientApp.csproj          # Frontend project configuration
├── README.md                     # Project documentation
└── REFLECTION.md                 # AI-assisted development reflection
```

## 🔌 API Endpoints

### Product Management

#### Get All Products
```http
GET /api/productlist
```

**Response:**
```json
[
  {
    "id": 1,
    "name": "Laptop",
    "price": 1200.50,
    "stock": 25,
    "category": {
      "id": 101,
      "name": "Electronics"
    }
  },
  {
    "id": 2,
    "name": "Headphones",
    "price": 50.00,
    "stock": 100,
    "category": {
      "id": 102,
      "name": "Accessories"
    }
  }
]
```

## 📊 Data Models

### Product Model
```csharp
public class Product
{
    public int Id { get; set; }
    public string Name { get; set; } = string.Empty;
    public double Price { get; set; }
    public int Stock { get; set; }
    public Category? Category { get; set; }
}
```

### Category Model
```csharp
public class Category
{
    public int Id { get; set; }
    public string? Name { get; set; }
}
```

## 🎮 How to Use

### 1. Backend API
- **Start the ServerApp** - Run the backend API server
- **API Documentation** - Access OpenAPI documentation at `/swagger`
- **Test Endpoints** - Use the provided `ServerApp.http` file for testing

### 2. Frontend Application
- **Start the ClientApp** - Run the Blazor WebAssembly application
- **Navigate to Products** - Visit `/fetchproducts` to view inventory
- **View Product Details** - See product information with categories

### 3. Development Workflow
- **API-First Development** - Backend API drives frontend functionality
- **CORS Configuration** - Properly configured for local development
- **Error Handling** - Comprehensive error management on both ends

## 🔧 Configuration

### CORS Policy
```csharp
// ServerApp/Program.cs
builder.Services.AddCors();

app.UseCors(policy =>
    policy.AllowAnyOrigin()
          .AllowAnyMethod()
          .AllowAnyHeader());
```

### HTTP Client Configuration
```csharp
// ClientApp/Program.cs
builder.Services.AddScoped(sp => new HttpClient { BaseAddress = new Uri(builder.HostEnvironment.BaseAddress) });
```

## 🤖 AI-Assisted Development Features

### Copilot Integration
- **Code Generation** - Automated API endpoint scaffolding
- **Debugging Assistance** - AI-powered problem-solving
- **Performance Optimization** - Suggested caching strategies
- **Best Practices** - Code quality and security recommendations

### Key Benefits
- **Reduced Development Time** - Faster code generation and debugging
- **Improved Code Quality** - AI-suggested best practices
- **Enhanced Learning** - Real-time guidance and explanations
- **Error Prevention** - Proactive issue identification

## 🧪 Testing

### API Testing
```bash
# Test the API endpoint
curl -X GET "https://localhost:7001/api/productlist"
```

### Frontend Testing
1. Navigate to the Blazor application
2. Visit the Products page
3. Verify data loading and display
4. Test error handling scenarios

## 🚀 Deployment

### Development
```bash
# Backend
cd ServerApp && dotnet run

# Frontend
cd ClientApp && dotnet run
```

### Production
```bash
# Build for production
dotnet publish -c Release

# Deploy to your preferred hosting platform
```

### Environment Variables
- `ASPNETCORE_ENVIRONMENT` - Environment mode (Development/Production)
- `ASPNETCORE_URLS` - Server URLs configuration

## 🤝 Contributing

1. **Fork the repository**
2. **Create a feature branch** (`git checkout -b feature/amazing-feature`)
3. **Commit your changes** (`git commit -m 'Add some amazing feature'`)
4. **Push to the branch** (`git push origin feature/amazing-feature`)
5. **Open a Pull Request**

### Development Guidelines
- Follow C# coding conventions
- Use proper error handling
- Test API endpoints thoroughly
- Ensure CORS configuration is correct
- Update documentation as needed

## 🔮 Future Enhancements

### Planned Features
- **Database Integration** - Entity Framework with SQL Server
- **Authentication System** - JWT-based user authentication
- **Advanced CRUD Operations** - Full product management
- **Real-time Updates** - SignalR integration
- **Advanced UI Components** - Rich Blazor components
- **Search and Filtering** - Product search functionality

### Technical Improvements
- **Database Migration** - Entity Framework migrations
- **API Versioning** - Versioned API endpoints
- **Caching Strategy** - Redis or in-memory caching
- **Logging and Monitoring** - Application insights
- **Unit Testing** - Comprehensive test coverage
- **CI/CD Pipeline** - Automated deployment

## 📝 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Microsoft** - ASP.NET Core and Blazor frameworks
- **Microsoft Copilot** - AI-assisted development support
- **Bootstrap Team** - Responsive CSS framework
- **.NET Community** - Continuous improvements and support

## 📚 Learning Resources

### Documentation
- [ASP.NET Core 9 Documentation](https://docs.microsoft.com/en-us/aspnet/core/)
- [Blazor WebAssembly Guide](https://docs.microsoft.com/en-us/aspnet/core/blazor/)
- [Minimal API Tutorial](https://docs.microsoft.com/en-us/aspnet/core/tutorials/min-web-api)

### AI-Assisted Development
- [Microsoft Copilot Documentation](https://docs.github.com/en/copilot)
- [AI-Assisted Coding Best Practices](https://docs.github.com/en/copilot/getting-started-with-github-copilot)

## 📞 Support

For questions, issues, or contributions:
- **Issues**: [GitHub Issues](https://github.com/SametDulger/InventoryHub/issues)
- **Discussions**: [GitHub Discussions](https://github.com/SametDulger/InventoryHub/discussions)

## 🌟 Key Highlights

### Modern Architecture
- **Full-Stack .NET** - Unified C# development experience
- **Minimal API** - High-performance, lightweight backend
- **Blazor WebAssembly** - Modern single-page application
- **AI-Assisted Development** - Microsoft Copilot integration

### Development Experience
- **Rapid Development** - AI-powered code generation
- **Debugging Support** - Intelligent problem-solving assistance
- **Best Practices** - AI-guided coding standards
- **Learning Enhancement** - Real-time development guidance

---

**Built with ❤️ using ASP.NET Core 9 and Blazor WebAssembly with Microsoft Copilot**
