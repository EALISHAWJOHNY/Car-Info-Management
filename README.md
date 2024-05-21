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
--------------------Values for table ------------------------
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
           (7, 107, 207, 307, 'Audi', 'A4', 'Sedan', 'I4', 252, 'Automatic', 27, 5, 'Driver, Passenger, Side', 480, 40000.00);
           ==============================================================================================================================================

           <%@ Page Title="Customer Data" Language="C#" MasterPageFile="~/Master.Master" AutoEventWireup="true" CodeBehind="Customer.aspx.cs" Inherits="CarInfoMang.Customer" %>

<asp:Content ID="Content1" ContentPlaceHolderID="head" runat="server">
    <style>
        #btnSearch{
            
                
        }
    </style>
</asp:Content>
<asp:Content ID="Content2" ContentPlaceHolderID="cphOpenSideNav" runat="server">
</asp:Content>
<asp:Content ID="Content3" ContentPlaceHolderID="cphSideNav" runat="server">
</asp:Content>
<asp:Content ID="Content4" ContentPlaceHolderID="cphBody" runat="server">

    <table class="w-100">
      <script type="text/javascript">
    function showTextbox() {
        var dropdown = document.getElementById('<%= ddlOptions.ClientID %>');
        var textbox = document.getElementById('<%= txtSearch.ClientID %>');
        if (dropdown.value !== "") {
            textbox.style.display = 'inline-block';
        }
        else {
            textbox.style.display = 'none';
        }
    }
     </script>
        <div style="background-color: darkgrey; padding-top: 20px; padding-bottom:20px; font-family:'Garamond'">
            <asp:DropDownList ID="ddlOptions" AppendDataBoundItems="true" runat="server" 
                AutoPostBack="true" OnSelectedIndexChanged="ddlOptions_SelectedIndexChanged" 
                onchange="showTextbox" Style="Height:40px; margin-left:10px">
  <asp:ListItem Text="Selected Option.." Value="0" />
  <asp:ListItem Text="Model" Value="1" />
  <asp:ListItem Text="Manufacture Name" Value="2" />
  <asp:ListItem Text="Type" Value="3" />
  </asp:DropDownList>
  <asp:TextBox ID="txtSearch" runat="server" Style="display:none; margin-left:10px; height:40px" placeholder="Enter Search term." OnTextChanged="txtSearch_TextChanged"></asp:TextBox>
  </asp:TextBox>
  <asp:Button  ID="btnSearch" runat="server" Style="height:40px; width:70px; border-radius:7px;" Text="Search"  OnClick="btnSearch_Click"/>  
        </div>           
    </table>
    <div>
        <asp:GridView runat="server" AutoGenerateColumns="False" DataSourceID="SqlDataSource1" DataKeyNames="CarId" AllowSorting="True" ID="gvGridView">
            <Columns>
                <asp:BoundField DataField="CarId" HeaderText="CarId" ReadOnly="True" SortExpression="CarId" />
                <asp:BoundField DataField="ManufacturerId" HeaderText="ManufacturerId" SortExpression="ManufacturerId" />
                <asp:BoundField DataField="CarTypeId" HeaderText="CarTypeId" SortExpression="CarTypeId" />
                <asp:BoundField DataField="TransmissionTypeId" HeaderText="TransmissionTypeId" SortExpression="TransmissionTypeId" />
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
            </Columns>
        </asp:GridView>
    </div>

    <asp:SqlDataSource ID="SqlDataSource1" runat="server" ConnectionString="<%$ ConnectionStrings:CIMSPROJECTConnectionString2 %>" SelectCommand="ListAllCars" SelectCommandType="StoredProcedure"></asp:SqlDataSource>

</asp:Content>



