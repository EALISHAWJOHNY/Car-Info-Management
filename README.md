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

<%@ Page Title="" Language="C#" MasterPageFile="~/MasterPageTemp.Master" AutoEventWireup="true" CodeBehind="CreateCar.aspx.cs" Inherits="CarInfoManagement.CreateCar" %>
<%@ Page Title="" Language="C#" MasterPageFile="~/MasterPageTemp.Master" AutoEventWireup="true" CodeBehind="CreateCar.aspx.cs" Inherits="CarInfoManagement.CreateCar" %>
<asp:Content ID="Content1" ContentPlaceHolderID="head" runat="server">
</asp:Content>
<asp:Content ID="Content2" ContentPlaceHolderID="cphOpenSideNav" runat="server">
</asp:Content>
<asp:Content ID="Content3" ContentPlaceHolderID="cphSideNav" runat="server">
</asp:Content>
<asp:Content ID="Content4" ContentPlaceHolderID="cphBody" runat="server">
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
                <h2 class="text-center">Create Car</h2>
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


----------------Add Car Admin

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
------------------------------
USE [CIMSPROJECT]
GO

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
           (<CarId, int,>
           ,<ManufacturerId, int,>
           ,<CarTypeId, int,>
           ,<TransmissionTypeId, int,>
           ,<ManufacturerName, nvarchar(255),>
           ,<Model, nvarchar(255),>
           ,<Type, nvarchar(50),>
           ,<Engine, char(4),>
           ,<BHP, int,>
           ,<Transmission, nvarchar(50),>
           ,<Mileage, int,>
           ,<Seat, int,>
           ,<AirBagDetails, nvarchar(255),>
           ,<BootSpace, int,>
           ,<Price, decimal(18,2),>)
GO




