# CinemaService_booking
Personal Cinema Booking Service


### Solution Structure
    CinemaServiceBooking.sln
    ├── CinemaServiceBooking.Web/             # App chính dùng Razor Pages
    ├── CinemaServiceBooking.Application/     # Xử lý logic nghiệp vụ
    ├── CinemaServiceBooking.Domain/          # Định nghĩa Entity, Interface
    ├── CinemaServiceBooking.Infrastructure/  # EF DbContext, Repository
    ├── CinemaServiceBooking.Logging/         # Logging wrapper
    ├── CinemaServiceBooking.Worker/          # Background tasks
    ├── CinemaServiceBooking.Contracts/       # Model dùng chung
    └── CinemaServiceBooking.Tests/           # xUnit test
    
    ##### Related References
        * Web cần gọi Application
        dotnet add CinemaServiceBooking.Web/CinemaServiceBooking.Web.csproj reference CinemaServiceBooking.Application/CinemaServiceBooking.Application.csproj

        * Application cần gọi Domain, Infrastructure, Logging, Contracts
        dotnet add CinemaServiceBooking.Application/CinemaServiceBooking.Application.csproj reference CinemaServiceBooking.Domain/CinemaServiceBooking.Domain.csproj
        dotnet add CinemaServiceBooking.Application/CinemaServiceBooking.Application.csproj reference CinemaServiceBooking.Infrastructure/CinemaServiceBooking.Infrastructure.csproj
        dotnet add CinemaServiceBooking.Application/CinemaServiceBooking.Application.csproj reference CinemaServiceBooking.Logging/CinemaServiceBooking.Logging.csproj
        dotnet add CinemaServiceBooking.Application/CinemaServiceBooking.Application.csproj reference CinemaServiceBooking.Contracts/CinemaServiceBooking.Contracts.csproj

        * Worker gọi Application
        dotnet add CinemaServiceBooking.Worker/CinemaServiceBooking.Worker.csproj reference CinemaServiceBooking.Application/CinemaServiceBooking.Application.csproj

        * Tests gọi Application & Infrastructure
        dotnet add CinemaServiceBooking.Tests/CinemaServiceBooking.Tests.csproj reference CinemaServiceBooking.Application/CinemaServiceBooking.Application.csproj
        dotnet add CinemaServiceBooking.Tests/CinemaServiceBooking.Tests.csproj reference CinemaServiceBooking.Infrastructure/CinemaServiceBooking.Infrastructure.csproj

