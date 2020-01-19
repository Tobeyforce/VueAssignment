<template>
  <div class="container-scroller">
    <div class="horizontal-menu">
      <nav class="navbar top-navbar col-lg-12 col-12 p-0">
        <div class="container">
          <div class="navbar-menu-wrapper d-flex align-items-center">
            <ul class="navbar-nav navbar-nav-right">
              <NavBarMessages />

              <NavBarNotifications />

              <NavBarProfileDropDown :name="name" />
            </ul>

            <button
              class="navbar-toggler navbar-toggler-right d-lg-none align-self-center"
              type="button"
              data-toggle="horizontal-menu-toggle"
            >
              <span class="mdi mdi-menu"></span>
            </button>
          </div>
        </div>
      </nav>
    </div>

    <div class="container-fluid page-body-wrapper">
      <div class="main-panel">
        <div class="content-wrapper">
          <div class="row">
            <div class="col-md-12 grid-margin">
              <WelcomeBanner :name="name" />
            </div>
          </div>

          <div class="row">
            <div class="col-xl-6 grid-margin">
              <div class="row">
                <div class="col-md-6 grid-margin stretch-card">
                  <Users />
                </div>
                <div class="col-md-6 grid-margin stretch-card">
                  <Projects />
                </div>
              </div>
              <div class="row">
                <div class="col-md-12 stretch-card">
                  <Downloads />
                </div>
              </div>
            </div>

            <div class="col-xl-6 grid-margin stretch-card">
              <TotalSalesChart />
            </div>
          </div>

          <div class="row">
            <div class="col-md-3 grid-margin stretch-card">
              <TotalSales />
            </div>
            <div class="col-md-3 grid-margin stretch-card">
              <TotalPurchases />
            </div>
            <div class="col-md-3 grid-margin stretch-card">
              <TotalGrowth />
            </div>
            <div class="col-md-3 grid-margin stretch-card">
              <TotalOrders />
            </div>
          </div>

          <div class="row">
            <div class="col-xl-8 grid-margin stretch-card">
              <Tickets />
            </div>
            <div class="col-xl-4 grid-margin stretch-card">
              <Updates />
            </div>
          </div>

          <div class="row">
            <div class="col-xl-3 grid-margin stretch-card">
              <Distribution />
            </div>

            <div class="col-xl-9 grid-margin stretch-card">
              <div class="card">
                <div class="row">
                  <div class="col-md-7 col-lg-6 col-xl-7">
                    <SaleReport />
                  </div>
                  <div class="col-md-5 col-lg-6 col-xl-5">
                    <SaleReportOverview />
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="row">
            <div class="col-md-12">
              <OpenInvoices />
            </div>
          </div>
        </div>

        <Footer />
      </div>
    </div>
  </div>
</template>

<script>
import TotalSalesChart from "./components/TotalSalesChart/TotalSalesChart";
import NavBarMessages from "./components/NavBar/NavBarMessage/NavBarMessages";
import NavBarNotifications from "./components/NavBar/NavBarNotifications/NavbarNotifications";
import NavBarProfileDropDown from "./components/NavBar/NavBarProfileDropDown/NavBarProfileDropDown";
import WelcomeBanner from "./components/WelcomeBanner/WelcomeBanner";
import Users from "./components/Users/Users";
import Projects from "./components/Projects/Projects";
import Downloads from "./components/Downloads/Downloads";
import Tickets from "./components/Tickets/Tickets";
import Updates from "./components/Updates/Updates";
import SaleReport from "./components/SaleReports/SaleReport";
import SaleReportOverview from "./components/SaleReports/SaleReportOverview";
import Distribution from "./components/Distribution/Distribution";
import OpenInvoices from "./components/OpenInvoices/OpenInvoices";
import Footer from "./components/Footer/Footer";
import TotalSales from "./components/ColorInfo/TotalSales";
import TotalPurchases from "./components/ColorInfo/TotalPurchases";
import TotalGrowth from "./components/ColorInfo/TotalGrowth";
import TotalOrders from "./components/ColorInfo/TotalOrders";

export default {
  name: "app",
  components: {
    TotalSalesChart,
    NavBarMessages,
    NavBarNotifications,
    NavBarProfileDropDown,
    WelcomeBanner,
    TotalSales,
    TotalPurchases,
    TotalGrowth,
    TotalOrders,
    Users,
    Projects,
    Downloads,
    Tickets,
    Updates,
    SaleReport,
    SaleReportOverview,
    Distribution,
    OpenInvoices,
    Footer
  },
  data() {
    return {
      name: String
    };
  },
  created() {
    fetch(
      "https://inlupp-fa.azurewebsites.net/api/users?firstname=Albin&lastname=Wetteus"
    )
      .then(res => res.text())
      .then(data => {
        this.name = data;
      });
  }
};
</script>
