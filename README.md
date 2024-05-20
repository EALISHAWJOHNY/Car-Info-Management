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
                    <asp:HyperLink CssClass="navbar-brand" runat="server" NavigateUrl="~/AdminDashboard.aspx">Car System</asp:HyperLink>
                </div>
                <ul class="nav-items">
                    <li class="nav-item">
                        <a class="nav-link" href="HomePage.aspx">Home</a>
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

        </div>

    </form>

    <script>

        function openSideNav() {

            var sideNav = document.getElementById("sideNav");

            sideNav.style.width = "250px";

            var sideNavOverlay = document.querySelectorAll("sidenav-overlay")[0];

            sideNavOverlay.style.width = "100%";

        }

        function closeSideNav() {

            var sideNav = document.getElementById("sideNav");

            sideNav.style.width = "0";

            var sideNavOverlay = document.querySelectorAll("sidenav-overlay")[0];

            sideNavOverlay.style.width = "0px";

        }

    </script>

</body>

</html>

---Car Entity
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

--Admin Login
<%@ Page Title="" Language="C#" MasterPageFile="~/NestedMasterPage1.master" AutoEventWireup="true" CodeBehind="WebForm2.aspx.cs" Inherits="CarInfoManagement.WebForm2" %>

<asp:Content ID="Content1" ContentPlaceHolderID="cphSideNavItems" runat="server">
    
    <ul class="navbar-nav">
        <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" id="navbardarkdropdownmenulink1" role="button" data-bs-toggle="dropdown" 
                aria-haspopup="true" aria-expanded="false">car info
            </a>
               <ul class="dropdown-menu" aria-labelledby="navbardarkdropdownmenulink1">
                <a class="dropdown-item" href="#">add</a>
                <a class="dropdown-item" href="#">update car info</a>
                <a class="dropdown-item" href="#">list</a>
                <a class="dropdown-item" href="#">delete car info</a>
            </ul>
        </li>

        <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" href="#" id="navbardarkdropdownmenulink2" role="button" data-bs-toggle="dropdown" aria-expanded="false">car transmission types
            </a>
            <ul class="dropdown-menu" aria-labelledby="navbardarkdropdownmenulink2">
                <li><a class="dropdown-item" href="#">add</a></li>
                <li><a class="dropdown-item" href="#">update</a></li>
                <li><a class="dropdown-item" href="#">list</a></li>
                <li><a class="dropdown-item" href="#">delete</a></li>
            </ul>
        </li>
        <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" href="#" id="navbardarkdropdownmenulink3" role="button" data-bs-toggle="dropdown" aria-expanded="false">car types
            </a>
            <ul class="dropdown-menu" aria-labelledby="navbardarkdropdownmenulink3">
                <li><a class="dropdown-item" href="#">add</a></li>
                <li><a class="dropdown-item" href="#">update</a></li>
                <li><a class="dropdown-item" href="#">list</a></li>
                <li><a class="dropdown-item" href="#">delete</a></li>
            </ul>
        </li>

    </ul>

</asp:Content>

