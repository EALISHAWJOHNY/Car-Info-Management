# Car-Info-Management

<%@ Master Language="C#" AutoEventWireup="true" CodeBehind="MasterPageTemp.Master.cs" Inherits="CarInfoManagement.MasterPageTemp" %>

<!DOCTYPE html>

<html>

<head runat="server">

    <title></title>

    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous" />

    <asp:ContentPlaceHolder ID="head" runat="server">
    </asp:ContentPlaceHolder>

    <style>
        body {
            padding-top: 69px;
        }

            body::-webkit-scrollbar {
                display: none;
            }

        .navbar {
            display: flex;
            justify-content: space-between;
            padding: 1% 3%;
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            box-shadow: 0 0 10px 0 #0000004d;
        }

        .navbar-brand {
            font-size: 1.8rem;
            font-family: Roboto, Arial, sans-serif;
            font-weight: bold;
        }

        .nav-link {
            font-size: 1.2rem;
            margin-left: 1.5rem;
            cursor: pointer;
        }

            .nav-link:hover {
                text-decoration: underline;
            }

        .nav-items {
            display: flex;
            align-items: center;
            list-style-type: none;
            margin: 0;
            padding: 0;
        }

        /*

        .sidenav-overlay {

            position: fixed;

            top: 0;

            left: 0;

            width: 0%;

            height: 100%;

            background-color: rgba(0, 0, 0, 0.5);

            z-index: 1010;

        }*/

        .sidenav {
            height: 100%;
            width: 0;
            position: fixed;
            z-index: 1001;
            top: 0;
            left: 0;
            overflow-x: hidden;
            transition: 0.5s;
            position: fixed;
            background-color: #ffffff;
            overflow-x: hidden;
            padding-top: 20px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
        }

            .sidenav a {
                padding: 8px 8px 8px 32px;
                text-decoration: none;
                font-size: 18px;
                color: #333333;
                display: block;
                white-space: nowrap;
            }

        .openbtn {
            font-size: 30px;
            cursor: pointer;
            color: #333333;
            padding: 20px;
            border: none;
        }

        .sidenav .closebtn {
            position: absolute;
            top: 10px;
            right: 20px;
            font-size: 24px;
            color: #666;
            cursor: pointer;
        }

        .sidenav-items {
            margin-top: 60px;
        }
    </style>

</head>

<body>

    <form id="form1" runat="server">

        <div>

            <nav class="navbar navbar-light bg-light">

                <div>
                    <asp:ContentPlaceHolder ID="cphOpenSideNav" runat="server"></asp:ContentPlaceHolder>
                    <asp:HyperLink CssClass="navbar-brand" runat="server" NavigateUrl="~/AdminDashboard.aspx">Car Infomartion Management System</asp:HyperLink>
                </div>
                <ul class="nav-items">
                    <li class="nav-item">
                        <a class="nav-link" href="WebForm1.aspx">Home</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="AdminLogin.aspx">Admin Login</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="Customer.aspx">Customer</a>
                    </li>
                </ul>
            </nav>
            <asp:ContentPlaceHolder ID="cphSideNav" runat="server"></asp:ContentPlaceHolder>

            <asp:ContentPlaceHolder ID="cphBody" runat="server">
            </asp:ContentPlaceHolder>
            <p style="text-align: center; margin-top: 30px;">&nbsp;</p>
            <p style="text-align: center; margin-top: 30px;">&nbsp;</p>
            <p style="text-align: center; margin-top: 30px;">&nbsp;</p>
            <p style="text-align: center; margin-top: 30px;">&nbsp;</p>
            <p style="text-align: center; margin-top: 30px;">&nbsp;</p>
            <p style="text-align: center; margin-top: 30px;">&nbsp;</p>
            <p style="text-align: center; margin-top: 30px;">&nbsp;</p>

        </div>
        <footer>
            <p class="text-center">&copy; <%: DateTime.Now.Year %> - Car Information Management System</p>
        </footer>

    </form>

    <script>

        function openSideNav() {

            var sideNav = document.getElementById("sideNav");

            sideNav.style.width = "250px";
        }

        function closeSideNav() {

            var sideNav = document.getElementById("sideNav");

            sideNav.style.width = "0";

        }

    </script>

</body>

</html>


**---Car Entity**

namespace Car_Info_Management
{
    public class CarInfo
    {
        public string manufacturerName { get; set; }
        public string model { get; set; }
        public string type { get; set; }
        public string engine { get; set; }
        public int bhp { get; set; }
        public string transmission { get; set; }
        public int mileage { get; set; }
        public int seats { get; set; }
        public string airBagDetails { get; set; }
        public int bootSpace { get; set; }
        public decimal price { get; set; }
    }
}

----HomePage

<%@ Page Title="" Language="C#" MasterPageFile="~/MasterPageTemp.Master" AutoEventWireup="true" CodeBehind="WebForm1.aspx.cs" Inherits="CarInfoManagement.WebForm1" %>
<asp:Content ID="Content1" ContentPlaceHolderID="head" runat="server">
</asp:Content>
<asp:Content ID="Content2" ContentPlaceHolderID="cphOpenSideNav" runat="server">
</asp:Content>
<asp:Content ID="Content3" ContentPlaceHolderID="cphSideNav" runat="server">
</asp:Content>
<asp:Content ID="Content4" ContentPlaceHolderID="cphBody" runat="server">
    <h1 style="text-align:center;margin-top:30px;">Welcome!</h1>
    
</asp:Content>

**--Admin Login**

<%@ Page Title="" Language="C#" MasterPageFile="~/NestedMasterPage1.master" AutoEventWireup="true" CodeBehind="WebForm2.aspx.cs" Inherits="CarInfoManagement.WebForm2" %>

<asp:Content ID="Content1" ContentPlaceHolderID="cphSideNavItems" runat="server">    
   <ul class="navbar-nav">
        <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" id="navbardarkdropdownmenulink1" role="button" data-bs-toggle="dropdown" aria-expanded="false">Car Info</a>
            <ul class="dropdown-menu" aria-labelledby="navbardarkdropdownmenulink1">
                <li><a class="dropdown-item" href="CreateCar.aspx">Add</a></li>
                <li><a class="dropdown-item" href="UpdateCar.aspx">Update Car Info</a></li>
                <li><a class="dropdown-item" href="ListCars.aspx">List</a></li>
                <li><a class="dropdown-item" href="DeleteCar.aspx">Delete Car Info</a></li>
            </ul>
        </li>
        <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" href="#" id="navbardarkdropdownmenulink2" role="button" data-bs-toggle="dropdown" aria-expanded="false">Car Transmission Types</a>
            <ul class="dropdown-menu" aria-labelledby="navbardarkdropdownmenulink2">
                <a class="dropdown-item" href="#">Add</a>
                <li><a class="dropdown-item" href="#">Update</a></li>
                <li><a class="dropdown-item" href="#">List</a></li>
                <li><a class="dropdown-item" href="#">Delete</a></li>
            </ul>
        </li>
        <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" href="#" id="navbardarkdropdownmenulink3" role="button" data-bs-toggle="dropdown" aria-expanded="false">Car Types</a>
            <ul class="dropdown-menu" aria-labelledby="navbardarkdropdownmenulink3">
                <li><a class="dropdown-item" href="#">Add</a></li>
                <li><a class="dropdown-item" href="#">Update</a></li>
                <li><a class="dropdown-item" href="#">List</a></li>
                <li><a class="dropdown-item" href="#">Delete</a></li>
            </ul>
        </li>
    </ul>
</asp:Content>

**---CreateCar(Admin)**

<%@ Page Title="" Language="C#" MasterPageFile="~/MasterPageMenu.master" AutoEventWireup="true" CodeBehind="CreateCarinfoAdmin.aspx.cs" Inherits="CarInfoManagement.CreateCarinfoAdmin" %>

<asp:Content ID="Content1" ContentPlaceHolderID="cphSideNavItems" runat="server">
    <ul class="navbar-nav">
        <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" id="navbardarkdropdownmenulink1" role="button" data-bs-toggle="dropdown" aria-expanded="false">Car Info</a>
            <ul class="dropdown-menu" aria-labelledby="navbardarkdropdownmenulink1">
                <li><a class="dropdown-item" href="CreateCarInfoAdmin.aspx">Add</a></li>
                <li><a class="dropdown-item" href="UpdateCarAdmin.aspx">Update Car Info</a></li>
                <li><a class="dropdown-item" href="ListCars.aspx">List</a></li>
                <li><a class="dropdown-item" href="DeleteCar.aspx">Delete Car Info</a></li>
            </ul>
        </li>
        <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" href="#" id="navbardarkdropdownmenulink2" role="button" data-bs-toggle="dropdown" aria-haspopup="true" aria-expanded="false">Car Transmission Types</a>
            <ul class="dropdown-menu" aria-labelledby="navbardarkdropdownmenulink2">
                <li><a href="#">Add</a></li>
                <li><a class="dropdown-item" href="#">Update</a></li>
                <li><a class="dropdown-item" href="#">List</a></li>
                <li><a class="dropdown-item" href="#">Delete</a></li>
            </ul>
        </li>
        <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" href="#" id="navbardarkdropdownmenulink3" role="button" data-bs-toggle="dropdown" aria-expanded="false">Car Types</a>
            <ul class="dropdown-menu" aria-labelledby="navbardarkdropdownmenulink3">
                <li><a class="dropdown-item" href="#">Add</a></li>
                <li><a class="dropdown-item" href="#">Update</a></li>
                <li><a class="dropdown-item" href="#">List</a></li>
                <li><a class="dropdown-item" href="#">Delete</a></li>
            </ul>
        </li>
    </ul>
</asp:Content>
<asp:Content ID="Content2" ContentPlaceHolderID="cphBody" runat="server">    
   
                <asp:Label ID="SuccessMessage" runat="server" Text="" ForeColor="Green" CssClass="float-end"></asp:Label>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <h2 class="text-center" style="margin-top:60px;">Create Car</h2>
                <div class="form-group">
                    <table class="table">
                        <tr>
                            <td>
                                <label id="lblManufactureId" for="ManufactureId" >Manufacturer</label>
                            </td>
                            <td>
                                <asp:DropDownList ID="ddlManufactureId" CssClass="form-control" runat="server" OnSelectedIndexChanged="ManufactureId_SelectedIndexChanged" />
                            </td>
                            <td>
                                &nbsp;</td>
                        </tr>
                        <tr>
                            <td>
                                <label id="lblModel" for="Model">Model</label>
                            </td>
                            <td>
                                <asp:TextBox ID="txtModel" runat="server" CssClass="form-control" OnTextChanged="Model_TextChanged" />
                            </td>
                        </tr>
                        <tr>
                            <td>
                                <label id="lblTypeId" for="TypeId">Type</label>
                            </td>
                            <td>
                                <asp:DropDownList ID="ddlTypeId" runat="server" CssClass="form-control" OnSelectedIndexChanged="TypeId_SelectedIndexChanged" />
                            </td>
                        </tr>
                        <tr>
                            <td>
                                <label Id="lblEngine" for="Engine">Engine</label>
                            </td>
                            <td>
                                <asp:TextBox ID="txtEngine" runat="server" CssClass="form-control" OnTextChanged="Engine_TextChanged" />
                            </td>
                        </tr>
                        <tr>
                            <td>
                                <label id="lblBHP" for="BHP">BHP</label>
                            </td>
                            <td>
                                <asp:TextBox ID="txtBHP" runat="server" CssClass="form-control" OnTextChanged="BHP_TextChanged" />
                            </td>
                        </tr>
                        <tr>
                            <td>
                                <label id="lblTransmission" for="TransmissionTypeId">Transmission Type</label>
                            </td>
                            <td>
                                <asp:DropDownList ID="ddlTransmissionTypeId" runat="server" CssClass="form-control" OnSelectedIndexChanged="TransmissionTypeId_SelectedIndexChanged" />
                            </td>
                        </tr>
                        <tr>
                            <td>
                                <label for="Mileage">Mileage</label>
                            </td>
                            <td>
                                <asp:TextBox ID="txtMileage" runat="server" CssClass="form-control" OnTextChanged="Mileage_TextChanged" />
                            </td>
                        </tr>
                        <tr>
                            <td>
                                <label for="Seats">Seats</label>
                            </td>
                            <td>
                                <asp:TextBox ID="txtSeats" runat="server" CssClass="form-control" OnTextChanged="Seats_TextChanged" />
                            </td>
                        </tr>
                        <tr>
                            <td>
                                <label for="AirBagDetails">Airbag Details</label>
                            </td>
                            <td>
                                <asp:TextBox ID="txtAirBagDetails" runat="server" CssClass="form-control" OnTextChanged="AirBagDetails_TextChanged" />
                            </td>
                        </tr>
                        <tr>
                            <td>
                                <label for="BootsSpace">Boot Space</label>
                            </td>
                            <td>
                                <asp:TextBox ID="txtBootsSpace" runat="server" CssClass="form-control" OnTextChanged="BootsSpace_TextChanged" />
                            </td>
                        </tr>
                        <tr>
                            <td>
                                <label for="Price">Showroom Price</label>
                            </td>
                            <td>
                                <asp:TextBox ID="txtPrice" runat="server" CssClass="form-control" OnTextChanged="Price_TextChanged" />
                            </td>
                        </tr>
                        <tr>
                            <td></td>
                            <td>
                                <asp:Button ID="btnCreateButton" runat="server" Text="Create" CssClass="btn btn-primary" OnClick="CreateButton_Click" />
                            </td>
                        </tr>
                        <tr>
                            <td>&nbsp;</td>                            
                        </tr>
                    </table>
                </div>
            </div>
        </div>
    </div>
</asp:Content>

**---Update Car Info Admin**

<%@ Page Title="" Language="C#" MasterPageFile="~/MasterPageTemp.Master" AutoEventWireup="true" CodeBehind="UpdateCarAdmin.aspx.cs" Inherits="CarInfoManagement.UpdateCarAdmin" %>
<asp:Content ID="Content1" ContentPlaceHolderID="head" runat="server">
</asp:Content>
<asp:Content ID="Content2" ContentPlaceHolderID="cphOpenSideNav" runat="server">
</asp:Content>
<asp:Content ID="Content3" ContentPlaceHolderID="cphSideNav" runat="server">
</asp:Content>
<asp:Content ID="Content4" ContentPlaceHolderID="cphBody" runat="server">
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <h2 class="text-center">Update Car Info</h2>
                <div class="form-group">
                    <table class="table">
                        <tr>
                            <td>
                                <label for="ManufactureId">Manufacturer</label>
                            </td>
                            <td>
                                <asp:TextBox ID="ManufactureId" runat="server" CssClass="form-control" />
                            </td>
                        </tr>
                        <tr>
                            <td>
                                <label for="Model">Model</label>
                            </td>
                            <td>
                                <asp:TextBox ID="Model" runat="server" CssClass="form-control" />
                            </td>
                        </tr>
                        <tr>
                            <td>
                                <label for="TypeId">Type</label>
                            </td>
                            <td>
                                <asp:DropDownList ID="TypeId" runat="server" CssClass="form-control" />
                            </td>
                        </tr>
                        <tr>
                            <td>
                                <label for="Engine">Engine</label>
                            </td>
                            <td>
                                <asp:TextBox ID="Engine" runat="server" CssClass="form-control" />
                            </td>
                        </tr>
                        <tr>
                            <td>
                                <label for="BHP">BHP</label>
                            </td>
                            <td>
                                <asp:TextBox ID="BHP" runat="server" CssClass="form-control" />
                            </td>
                        </tr>
                        <tr>
                            <td>
                                <label for="TransmissionTypeId">Transmission Type</label>
                            </td>
                            <td>
                                <asp:DropDownList ID="TransmissionTypeId" runat="server" CssClass="form-control" />
                            </td>
                        </tr>
                        <tr>
                            <td>
                                <label for="Mileage">Mileage</label>
                            </td>
                            <td>
                                <asp:TextBox ID="Mileage" runat="server" CssClass="form-control" />
                            </td>
                        </tr>
                        <tr>
                            <td>
                                <label for="Seats">Seats</label>
                            </td>
                            <td>
                                <asp:TextBox ID="Seats" runat="server" CssClass="form-control" />
                            </td>
                        </tr>
                        <tr>
                            <td>
                                <label for="AirBagDetails">Airbag Details</label>
                            </td>
                            <td>
                                <asp:TextBox ID="AirBagDetails" runat="server" CssClass="form-control" />
                            </td>
                        </tr>
                        <tr>
                            <td>
                                <label for="BootsSpace">Boot Space</label>
                            </td>
                            <td>
                                <asp:TextBox ID="BootsSpace" runat="server" CssClass="form-control" />
                            </td>
                        </tr>
                        <tr>
                            <td>
                                <label for="Price">Showroom Price</label>
                            </td>
                            <td>
                                <asp:TextBox ID="Price" runat="server" CssClass="form-control" />
                            </td>
                        </tr>
                        <tr>
                            <td></td>
                            <td>
                                <asp:Button ID="CreateButton" runat="server" Text="Create" CssClass="btn btn-primary" />
                            </td>
                        </tr>
                    </table>
                </div>
            </div>
        </div>
    </div>
</asp:Content>

---------------------------------------------------------------------------------
**Create table car** 

CREATE TABLE [dbo].[Car](
	[CarId] [int] IDENTITY(1,1) NOT NULL,
	[ManufacturerId] [int] NOT NULL,
	[CarTypeId] [int] NOT NULL,
	[TransmissionTypeId] [int] NOT NULL,
	[ManufacturerName] [nvarchar](255) NOT NULL,
	[Model] [nvarchar](255) NOT NULL,
	[Type] [nvarchar](50) NOT NULL,
	[Engine] [char](4) NOT NULL,
	[BHP] [int] NOT NULL,
	[Transmission] [nvarchar](50) NOT NULL,
	[Mileage] [int] NOT NULL,
	[Seat] [int] NOT NULL,
	[AirBagDetails] [nvarchar](255) NOT NULL,
	[BootSpace] [int] NOT NULL,
	[Price] [decimal](18, 2) NOT NULL,
PRIMARY KEY CLUSTERED 
(
	[CarId] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY],
UNIQUE NONCLUSTERED 
(
	[Model] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO

ALTER TABLE [dbo].[Car]  WITH CHECK ADD FOREIGN KEY([CarTypeId])
REFERENCES [dbo].[CarType] ([Id])
GO

ALTER TABLE [dbo].[Car]  WITH CHECK ADD FOREIGN KEY([ManufacturerId])
REFERENCES [dbo].[Manufacturer] ([Id])
GO

ALTER TABLE [dbo].[Car]  WITH CHECK ADD FOREIGN KEY([TransmissionTypeId])
REFERENCES [dbo].[CarTransmissionType] ([Id])
GO

ALTER TABLE [dbo].[Car]  WITH CHECK ADD CHECK  (([Engine] like '[0-9].[0-9]L'))
GO

ALTER TABLE [dbo].[Car]  WITH CHECK ADD CHECK  (([Transmission]='Automatic' OR [Transmission]='Manual'))
GO
----------------**Add Car Admin**---------------------------

ALTER PROCEDURE [dbo].[AddCar]
@CarId int,
@ManufacturerId int,
@CarTypeId int,
@TransmissiontypeID int,
@Model nvarchar(100),
@Type nvarchar(50),
@Engine nvarchar(4),
@BHP int,
@Transmission nvarchar(50),
@Mileage int,
@Seats int,
@AirBagDetails nvarchar(255),
@BootSpace int,
@Price decimal(18,2)
AS 
BEGIN
    -- Declare a variable to hold the ManufacturerName
    DECLARE @ManufacturerName nvarchar(100);

    -- Select the ManufacturerName from the Manufacturer table
    SELECT @ManufacturerName = ManufacturerName
    FROM Manufacturer
    WHERE ManufacturerId = @ManufacturerId;

    -- Insert the values into the Car table
    INSERT INTO Car (CarId, ManufacturerId, CarTypeId, TransmissiontypeID, ManufacturerName, Model, Type, Engine, BHP, Transmission, Mileage, Seats, AirBagDetails, BootSpace, Price)
    VALUES (@CarId, @ManufacturerId, @CarTypeId, @TransmissiontypeID, @ManufacturerName, @Model, @Type, @Engine, @BHP, @Transmission, @Mileage, @Seats, @AirBagDetails, @BootSpace, @Price);
END
--------------------**Values for table Car** ------------------------
-- Insert sample data into the Car table
INSERT INTO [dbo].[Car]
           ([CarId]
           ,[ManufacturerId]
           ,[CarTypeId]
           ,[TransmissionTypeId]
           ,[ManufacturerName]
           ,[Model]
           ,[Type]
           ,[Engine]
           ,[BHP]
           ,[Transmission]
           ,[Mileage]
           ,[Seat]
           ,[AirBagDetails]
           ,[BootSpace]
           ,[Price])
     VALUES
           (1, 101, 201, 301, 'Toyota', 'Corolla', 'Sedan', 'V6', 180, 'Automatic', 30, 5, 'Driver, Passenger', 470, 20000.00),
           (2, 102, 202, 302, 'Honda', 'Civic', 'Sedan', 'I4', 160, 'Manual', 32, 5, 'Driver, Passenger', 450, 22000.00),
           (3, 103, 203, 303, 'Ford', 'Mustang', 'Coupe', 'V8', 450, 'Automatic', 20, 4, 'Driver, Passenger, Side', 380, 35000.00),
           (4, 104, 204, 304, 'Chevrolet', 'Tahoe', 'SUV', 'V8', 355, 'Automatic', 15, 7, 'Driver, Passenger, Side', 1220, 50000.00),
           (5, 105, 205, 305, 'Tesla', 'Model S', 'Sedan', 'Electric', 762, 'Automatic', 102, 5, 'Driver, Passenger, Side', 804, 80000.00),
           (6, 106, 206, 306, 'BMW', 'X5', 'SUV', 'I6', 335, 'Automatic', 24, 5, 'Driver, Passenger, Side', 650, 60000.00),
           (7, 107, 207, 307, 'Audi', 'A4', 'Sedan', 'I4', 252, 'Automatic', 27, 5, 'Driver, Passenger, Side', 480, 40000.00)

*------------------------------------ **Customer List**

<%@ Page Title="Customer Data" Language="C#" MasterPageFile="~/Master.Master" AutoEventWireup="true" CodeBehind="Customer.aspx.cs" Inherits="CarInfoMang.Customer" %>

<asp:Content ID="Content1" ContentPlaceHolderID="head" runat="server">
    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" integrity="sha384-RX8tVZWlpIFXvsIUTzy1I1FbGlpDi9l0r6mVFTGOYsOUtHe+WmB+6o3Jz6S9krHb" crossorigin="anonymous">
    <!-- DataTables CSS -->
    <link rel="stylesheet" href="https://cdn.datatables.net/1.10.24/css/dataTables.bootstrap5.min.css" />
    <style>
        #btnSearch {
            /* Add custom styles for the search button if needed */
        }
    </style>
</asp:Content>

<asp:Content ID="Content2" ContentPlaceHolderID="cphOpenSideNav" runat="server">
</asp:Content>

<asp:Content ID="Content3" ContentPlaceHolderID="cphSideNav" runat="server">
</asp:Content>

<asp:Content ID="Content4" ContentPlaceHolderID="cphBody" runat="server">
    <div class="container mt-4">
        <div class="row">
            <div class="col-12">
                <div style="background-color: darkgrey; padding: 20px; font-family: 'Garamond'">
                    <asp:DropDownList ID="ddlOptions" AppendDataBoundItems="true" runat="server" 
                        AutoPostBack="true" OnSelectedIndexChanged="ddlOptions_SelectedIndexChanged" 
                        class="form-select" style="width: auto; display: inline-block;">
                        <asp:ListItem Text="Selected Option.." Value="0" />
                        <asp:ListItem Text="Model" Value="1" />
                        <asp:ListItem Text="Manufacture Name" Value="2" />
                        <asp:ListItem Text="Type" Value="3" />
                    </asp:DropDownList>
                    <asp:TextBox ID="txtSearch" runat="server" class="form-control d-none" placeholder="Enter Search term." OnTextChanged="txtSearch_TextChanged" style="display:inline-block; width: auto;"></asp:TextBox>
                    <asp:Button ID="btnSearch" runat="server" class="btn btn-primary" Text="Search" OnClick="btnSearch_Click" />
                </div>
                <div class="mt-3">
                    <asp:GridView runat="server" AutoGenerateColumns="False" DataKeyNames="CarId" AllowSorting="False" ID="gvGridView" CssClass="table table-striped table-bordered">
                        <Columns>
                            <asp:BoundField DataField="CarId" HeaderText="CarId" ReadOnly="True" />
                            <asp:BoundField DataField="ManufacturerId" HeaderText="ManufacturerId" />
                            <asp:BoundField DataField="CarTypeId" HeaderText="CarTypeId" />
                            <asp:BoundField DataField="TransmissionTypeId" HeaderText="TransmissionTypeId" />
                            <asp:BoundField DataField="ManufacturerName" HeaderText="ManufacturerName" />
                            <asp:BoundField DataField="Model" HeaderText="Model" />
                            <asp:BoundField DataField="Type" HeaderText="Type" />
                            <asp:BoundField DataField="Engine" HeaderText="Engine" />
                            <asp:BoundField DataField="BHP" HeaderText="BHP" />
                            <asp:BoundField DataField="Transmission" HeaderText="Transmission" />
                            <asp:BoundField DataField="Mileage" HeaderText="Mileage" />
                            <asp:BoundField DataField="Seat" HeaderText="Seat" />
                            <asp:BoundField DataField="AirBagDetails" HeaderText="AirBagDetails" />
                            <asp:BoundField DataField="BootSpace" HeaderText="BootSpace" />
                            <asp:BoundField DataField="Price" HeaderText="Price" />
                        </Columns>
                    </asp:GridView>
                </div>
            </div>
        </div>
    </div>

    <!-- jQuery -->
    <script src="https://code.jquery.com/jquery-3.5.1.js"></script>
    <!-- Bootstrap Bundle with Popper -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-qptG4BRNaSK1rmDpZ++/xrFwAFGhgfsfZ9sx2PqnE/4yCTpyJffoDjjk+N5t9ggd" crossorigin="anonymous"></script>
    <!-- DataTables JS -->
    <script src="https://cdn.datatables.net/1.10.24/js/jquery.dataTables.min.js"></script>
    <script src="https://cdn.datatables.net/1.10.24/js/dataTables.bootstrap5.min.js"></script>

    <script type="text/javascript">
        $(document).ready(function () {
            $('#<%= gvGridView.ClientID %>').DataTable({
                "paging": true,
                "searching": false,
                "ordering": true,
                "columns": [
                    null,
                    null,
                    null,
                    null,
                    { "orderable": true }, // Enable sorting on ManufacturerName
                    null,
                    null,
                    null,
                    null,
                    null,
                    null,
                    null,
                    null,
                    null,
                    null
                ]
            });
        });

        function showTextbox() {
            var dropdown = document.getElementById('<%= ddlOptions.ClientID %>');
            var textbox = document.getElementById('<%= txtSearch.ClientID %>');
            if (dropdown.value !== "0") {
                textbox.style.display = 'inline-block';
            } else {
                textbox.style.display = 'none';
            }
        }
    </script>
</asp:Content>
    
--------------------------------------------**ADMIN LIST CAR**------------------------------

<%@ Page Title="" Language="C#" MasterPageFile="~/MasterPageMenu.Master" AutoEventWireup="true" CodeBehind="AdminListCar.aspx.cs" Inherits="CarInfoManagement.AdminListCar" %>

<asp:Content ID="Content1" ContentPlaceHolderID="head" runat="server">
</asp:Content>
<asp:Content ID="Content2" ContentPlaceHolderID="cphOpenSideNav" runat="server">
</asp:Content>
<asp:Content ID="Content3" ContentPlaceHolderID="cphSideNav" runat="server">
</asp:Content>
<asp:Content ID="Content4" ContentPlaceHolderID="cphSideNavItems" runat="server">
</asp:Content>
<asp:Content ID="Content5" ContentPlaceHolderID="cphBody" runat="server">
    <div class="container mt-4">
        <div class="row">
            <div class="col-12">
                <div class="mt-3" id="actions">
                    <div class="rowButtonAddNew">                       
                        <div class="col-sm-12 text-right mb-3">
                            <asp:button type="button" runat="server" commandName="AddCar"  text="Add New" class="btn btn-info" OnClick="AddNew_Click"></asp:button>
                        </div>
                    </div>                  

                    <asp:GridView CssClass="table table-striped" ID="gvCarList" runat="server" AutoGenerateColumns="False" OnRowCommand="ListCarInfo_RowCommand" DataKeyNames="CarId" DataSourceID="SqlDataSource1" OnSelectedIndexChanged="gvCarList_SelectedIndexChanged" AllowSorting="True">
                        <Columns>
                            <asp:BoundField DataField="CarId" HeaderText="CarId" InsertVisible="False" ReadOnly="True" SortExpression="CarId" Visible="False" />
                            <asp:BoundField DataField="ManufacturerId" HeaderText="ManufacturerId" SortExpression="ManufacturerId" Visible="False" />
                            <asp:BoundField DataField="CarTypeId" HeaderText="CarTypeId" SortExpression="CarTypeId" Visible="False" />
                            <asp:BoundField DataField="TransmissionTypeId" HeaderText="TransmissionTypeId" SortExpression="TransmissionTypeId" Visible="False" />
                            <asp:BoundField DataField="ManufacturerName" HeaderText="ManufacturerName" SortExpression="ManufacturerName" />
                            <asp:BoundField DataField="Model" HeaderText="Model" SortExpression="Model" />
                            <asp:BoundField DataField="Type" HeaderText="Type" SortExpression="Type" />
                            <asp:BoundField DataField="Engine" HeaderText="Engine" SortExpression="Engine" />
                            <asp:BoundField DataField="BHP" HeaderText="BHP" SortExpression="BHP" />
                            <asp:BoundField DataField="Transmission" HeaderText="Transmission" SortExpression="Transmission" />
                            <asp:BoundField DataField="Mileage" HeaderText="Mileage" SortExpression="Mileage" />
                            <asp:BoundField DataField="Seat" HeaderText="Seat" SortExpression="Seat" />
                            <asp:BoundField DataField="AirBagDetails" HeaderText="AirBagDetails" SortExpression="AirBagDetails" />
                            <asp:BoundField DataField="BootSpace" HeaderText="BootSpace" SortExpression="BootSpace" />
                            <asp:BoundField DataField="Price" HeaderText="Price" SortExpression="Price" />
                            <asp:TemplateField HeaderText="Actions">
                                <ItemTemplate>
                                    <asp:Button CssClass="btn btn-primary" ID="editBtn" runat="server" Text="Edit" CommandName="EditRow" CommandArgument='<%# Eval("CarId") %>' />
                                    <asp:Button CssClass="btn btn-primary" ID="deleteBtn" runat="server" Text="Delete" CommandName="DeleteRow" CommandArgument='<%# Eval("CarID") %>' />
                                </ItemTemplate>
                            </asp:TemplateField>
                        </Columns>
                    </asp:GridView>
                </div>
            </div>
        </div>
    </div>

    <!-- jQuery -->
    <script src="https://code.jquery.com/jquery-3.5.1.js"></script>
    <!-- Bootstrap Bundle with Popper -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-qptG4BRNaSK1rmDpZ++/xrFwAFGhgfsfZ9sx2PqnE/4yCTpyJffoDjjk+N5t9ggd" crossorigin="anonymous"></script>
    <!-- DataTables JS -->
    <script src="https://cdn.datatables.net/1.10.24/js/jquery.dataTables.min.js"></script>
    <script src="https://cdn.datatables.net/1.10.24/js/dataTables.bootstrap5.min.js"></script>

    <script type="text/javascript">
        $(document).ready(function () {
            $('#<%= gvCarList.ClientID %>').DataTable({
                "paging": true,
                "searching": false,
                "ordering": true,
                "columns": [
                    null,
                    null,
                    null,
                    null,
                    { "orderable": true }, // Enable sorting on ManufacturerName
                    null,
                    null,
                    null,
                    null,
                    null,
                    null,
                    null,
                    null,
                    null,
                    null
                ]
            });
        });
    </script>
    <asp:SqlDataSource ID="SqlDataSource1" runat="server" ConnectionString="<%$ ConnectionStrings:Car_ManagementConnectionString2 %>" SelectCommand="AdminListCar" SelectCommandType="StoredProcedure"></asp:SqlDataSource>
</asp:Content>





--------------------------------------------
**UpdateAdminCarInfo**

ALTER PROCEDURE [dbo].[AdminUpdateCar](
    @CarId int,
    @ManufacturerId int,
    @CarTypeId int,
    @TransmissiontypeID int,
    @Model nvarchar(100),
    @Engine nvarchar(4),
    @BHP int,
    @Mileage int,
    @Seats int,
    @AirBagDetails nvarchar(255),
    @BootSpace int,
    @Price decimal(18,2),
    @result int output
)
AS 
BEGIN
    -- Declare variables to hold the ManufacturerName, Transmission, and CarType
    DECLARE @ManufacturerName nvarchar(100);
    DECLARE @Transmission nvarchar(100);
    DECLARE @CarType nvarchar(100);

    -- Select the ManufacturerName from the Manufacturer table
    SELECT @ManufacturerName = Name
    FROM Manufacturer
    WHERE Id = @ManufacturerId;

    -- Select the Transmission from the CarTransmissionType table
    SELECT @Transmission = Type
    FROM CarTransmissionType
    WHERE Id = @TransmissiontypeID;

    -- Select the CarType from the CarType table
    SELECT @CarType = Type
    FROM CarType
    WHERE Id = @CarTypeId;

    -- Check if the CarId exists in the Car table
    IF EXISTS (SELECT 1 FROM [dbo].[Car] WHERE CarId = @CarId)
    BEGIN
        -- Update the values in the Car table
        UPDATE Car
        SET ManufacturerId = @ManufacturerId,
            CarTypeId = @CarTypeId,
            TransmissiontypeID = @TransmissiontypeID,
            ManufacturerName = @ManufacturerName,
            Model = @Model,
            Type = @CarType,
            Engine = @Engine,
            BHP = @BHP,
            Transmission = @Transmission,
            Mileage = @Mileage,
            Seat = @Seats,
            AirBagDetails = @AirBagDetails,
            BootSpace = @BootSpace,
            Price = @Price
        WHERE CarId = @CarId;

        SET @result = 1;
    END
    ELSE
    BEGIN
        SET @result = 0;
    END

    RETURN @result;
END


-----------------------------

 <%@ Page Title="" Language="C#" MasterPageFile="~/MasterPageTemp.Master" AutoEventWireup="true" CodeBehind="AdminLogin.aspx.cs" Inherits="CarInfoManagement.AdminLogin" %>

<asp:Content ID="Content1" ContentPlaceHolderID="head" runat="server">
    <link href="//maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" rel="stylesheet" id="bootstrap-css">
    <script src="//maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js"></script>
    <script src="//cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
    <style>
        .wrapper {
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
            background-color: #f8f9fa;
        }
        #formContent {
            background: #fff;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 10px 20px 0 rgba(0, 0, 0, 0.1);
        }
        .fadeIn {
            animation: fadeIn ease-in 1;
        }
        .fadeIn.second {
            animation-delay: 0.2s;
        }
        .fadeIn.first {
            animation-delay: 0.1s;
        }
        .fadeIn.fourth {
            animation-delay: 0.4s;
        }
        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }
    </style>
</asp:Content>
<asp:Content ID="Content2" ContentPlaceHolderID="cphOpenSideNav" runat="server">
</asp:Content>
<asp:Content ID="Content3" ContentPlaceHolderID="cphSideNav" runat="server">
</asp:Content>
<asp:Content ID="Content4" ContentPlaceHolderID="cphSideNavItems" runat="server">
</asp:Content>
<asp:Content ID="Content5" ContentPlaceHolderID="cphBody" runat="server">
    <div class="wrapper fadeInDown">
        <div id="formContent" style="margin-top: 30px;">
            <!-- Login Form -->
            <div style="margin-top: 70px;">
                <asp:TextBox ID="Username" runat="server" CssClass="form-control fadeIn second" placeholder="login" />
                <asp:TextBox ID="Password" runat="server" CssClass="form-control fadeIn first" TextMode="Password" placeholder="password" />
                <asp:Button ID="button" runat="server" CssClass="btn btn-primary fadeIn fourth" Text="Login" OnClick="button_Click" />
            </div>
            <div class="form-group">
                <asp:Label ID="ErrorMessage" runat="server" Text="" ForeColor="Red"></asp:Label>
            </div>
        </div>
    </div>
</asp:Content>

--------------------------------------
**transmission list**

<%@ Page Title="" Language="C#" MasterPageFile="~/MasterPageMenu.Master" AutoEventWireup="true" CodeBehind="AdminCarInfoTransList.aspx.cs" Inherits="CarInfoManagement.AdminCarInfoTransList" %>

<asp:Content ID="Content1" ContentPlaceHolderID="head" runat="server">
</asp:Content>
<asp:Content ID="Content2" ContentPlaceHolderID="cphOpenSideNav" runat="server">
</asp:Content>
<asp:Content ID="Content3" ContentPlaceHolderID="cphSideNav" runat="server">
</asp:Content>
<asp:Content ID="Content4" ContentPlaceHolderID="cphSideNavItems" runat="server">
</asp:Content>
<asp:Content ID="Content5" ContentPlaceHolderID="cphBody" runat="server">
    <div class="container mt-4">
        <div class="row">
            <div class="col-12">
                <div class="mt-3" id="actions">
                    <div class="rowButtonAddNew">
                        <div class="col-sm-12 text-right mb-3">
                            <asp:LinkButton type="button" runat="server" CommandName="AddCar" class="btn btn-info" OnClick="AddNew_Click"><i class="bi bi-plus"></i>AddNew</asp:LinkButton>
                        </div>
                        <div class="rowButtonAddNew">
                            <asp:Label ID="SuccessMessage" runat="server" ForeColor="Green" CssClass="float-lg-end"></asp:Label>
                        </div>
                    </div>
                    <asp:GridView ID="GridView1" CssClass="table table-striped" runat="server" AllowSorting="True" AutoGenerateColumns="False" OnRowCommand="ListCarTransmission_RowCommand" DataKeyNames="Id" DataSourceID="SqlDataSource1" OnSelectedIndexChanged="GridView1_SelectedIndexChanged" Width="1008px">
                        <Columns>
                            <asp:BoundField DataField="Id" HeaderText="Id" InsertVisible="False" ReadOnly="True" SortExpression="Id" Visible="False" />
                            <asp:BoundField DataField="Type" HeaderText="Type" SortExpression="Type" />
                            <asp:TemplateField HeaderText="Actions">
                                <ItemTemplate>
                                    <asp:Button CssClass="btn btn-primary" ID="editBtn" runat="server" Text="Edit" CommandName="EditRow1" CommandArgument='<%# Eval("Id") %>' />
                                    <asp:Button CssClass="btn btn-primary" ID="deleteBtn" runat="server" Text="Delete" CommandName="DeleteRow1" CommandArgument='<%# Eval("Id") %>' />
                                </ItemTemplate>
                            </asp:TemplateField>
                        </Columns>
                    </asp:GridView>
                </div>
            </div>
        </div>
    </div>
    <!-- jQuery -->
    <script src="https://code.jquery.com/jquery-3.5.1.js"></script>
    <!-- Bootstrap Bundle with Popper -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-qptG4BRNaSK1rmDpZ++/xrFwAFGhgfsfZ9sx2PqnE/4yCTpyJffoDjjk+N5t9ggd" crossorigin="anonymous"></script>
    <!-- DataTables JS -->
    <script src="https://cdn.datatables.net/1.10.24/js/jquery.dataTables.min.js"></script>
    <script src="https://cdn.datatables.net/1.10.24/js/dataTables.bootstrap5.min.js"></script>

    <script type="text/javascript">
        $(document).ready(function () {
            $('#<%= GridView1.ClientID %>').DataTable({
                "paging": true,
                "searching": false,
                "ordering": true,
                "columns": [
                    null,
                    null,
                    null,
                    null,
                    { "orderable": true }, // Enable sorting on ManufacturerName
                    null,
                    null,
                    null,
                    null,
                    null,
                    null,
                    null,
                    null,
                    null,
                    null
                ]
            });
        });
</script>
    <asp:SqlDataSource ID="SqlDataSource1" runat="server" ConnectionString="<%$ ConnectionStrings:Car_ManagementConnectionString2 %>" SelectCommand="AdminListCarTrans" SelectCommandType="StoredProcedure" OnSelecting="SqlDataSource1_Selecting"></asp:SqlDataSource>

</asp:Content>

 protected void DisplayCarTransmissionType()
 {
     SqlConnection objCon = new SqlConnection("server=(localdb)\\local; database=Car_Management; integrated security=true");
     SqlCommand objCom = new SqlCommand("Select Type,Id from CarTransmissionType ", objCon); //here we are using stored procedure craeted in db 
     /*objCom.CommandType = CommandType;*/ //mentioning command type is a stored procedure
     objCon.Open();
     SqlDataReader objDRSearch = objCom.ExecuteReader();
     DataTable objDT = new DataTable();
     objDT.Load(objDRSearch);
     objCon.Close();
     ddlTransmissionTypeId.DataSource = objDT.DefaultView; //it returns the table as it is 
     ddlTransmissionTypeId.DataTextField = "Type";
     ddlTransmissionTypeId.DataValueField = "Id";
     ddlTransmissionTypeId.DataBind();
 }
public List<CarType> DisplayCarType()
{
    List<CarType> carTypes = new List<CarType>();
    using (SqlConnection objCon = new SqlConnection("server=(localdb)\\local; database=Car_Management; integrated security=true"))
    {
        using (SqlCommand objCom = new SqlCommand("p_allgetCarType", objCon))
        {
            objCom.CommandType = CommandType.StoredProcedure; // Set the command type to stored procedure
            objCon.Open();
            using (SqlDataReader objDRSearch = objCom.ExecuteReader())
            {
                DataTable objDT = new DataTable();
                objDT.Load(objDRSearch);
                objCon.Close();
                
                foreach (DataRow row in objDT.Rows)
                {
                    CarType carType = new CarType
                    {
                        Id = Convert.ToInt32(row["Id"]),
                        Type = row["Type"].ToString()
                    };
                    carTypes.Add(carType);
                }
            }
        }
    }
    return carTypes;
}


