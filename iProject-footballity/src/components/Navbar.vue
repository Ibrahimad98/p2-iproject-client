<script>
import { mapActions } from "pinia";
import { useFootballStore } from "../stores/football";

export default {
  name: "Navbar",
  methods: {
    ...mapActions(useFootballStore, ["changePage", "logOut"]),
  },
};
</script>
<template>
  <nav class="navbar navbar-dark bg-dark fixed-top">
    <div class="container-fluid">
      <img style="width: 30px" src="../assets/football-2-256.png" alt="..." />
      <a style="color: green" class="navbar-brand" href="#"
        ><strong>Footballity</strong></a
      >
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="offcanvas"
        data-bs-target="#offcanvasDarkNavbar"
        aria-controls="offcanvasDarkNavbar"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div
        class="offcanvas offcanvas-end text-bg-dark"
        tabindex="-1"
        id="offcanvasDarkNavbar"
        aria-labelledby="offcanvasDarkNavbarLabel"
      >
        <div class="offcanvas-header">
          <h5 class="offcanvas-title" id="offcanvasDarkNavbarLabel">Menu</h5>
          <button
            type="button"
            class="btn-close btn-close-white"
            data-bs-dismiss="offcanvas"
            aria-label="Close"
          ></button>
        </div>
        <div class="offcanvas-body">
          <ul class="navbar-nav justify-content-end flex-grow-1 pe-3">
            <li class="nav-item">
              <a
                @click.prevent="changePage('/')"
                class="nav-link active"
                aria-current="page"
                href="#"
                >Home</a
              >
            </li>
            <li class="nav-item">
              <a
                @click.prevent="changePage('/bookmarks')"
                class="nav-link"
                href="#"
                >My Team</a
              >
            </li>
            <li class="nav-item">
              <a
                @click.prevent="changePage('/positionForm')"
                class="nav-link"
                href="#"
                >Add your team</a
              >
            </li>
            <li class="nav-item">
              <a
                @click.prevent="changePage('/searchPlayer')"
                class="nav-link"
                href="#"
                >Search a player</a
              >
            </li>
            <li class="nav-item">
              <a @click.prevent="logOut" class="nav-link" href="#">Logout</a>
            </li>
            <!-- <li class="nav-item dropdown">
              <a
                class="nav-link dropdown-toggle"
                href="#"
                role="button"
                data-bs-toggle="dropdown"
                aria-expanded="false"
              >
                Dropdown
              </a>
              <ul class="dropdown-menu dropdown-menu-dark">
                <li><a class="dropdown-item" href="#">Action</a></li>
                <li><a class="dropdown-item" href="#">Another action</a></li>
                <li>
                  <hr class="dropdown-divider" />
                </li>
                <li>
                  <a class="dropdown-item" href="#">Something else here</a>
                </li>
              </ul>
            </li> -->
          </ul>
          <!-- <form class="d-flex mt-3" role="search">
            <input
              class="form-control me-2"
              type="search"
              placeholder="Search"
              aria-label="Search"
            />
            <button class="btn btn-success" type="submit">Search</button>
          </form> -->
        </div>
      </div>
    </div>
  </nav>
</template>
