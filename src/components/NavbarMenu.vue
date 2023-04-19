<template>
    <nav class="navbar navbar-expand-lg navbar-light navbar-sticky" id="mainNav">
        <div class="container px-4 px-lg-5">
            <a class="navbar-brand" href="/" >
             <h1>Tv Maze</h1>
            </a>
         
            <button
            style="color: white;"
                class="navbar-toggler"
                type="button"
                data-bs-toggle="collapse"
                data-bs-target="#navbarResponsive"
                aria-controls="navbarResponsive"
                aria-expanded="false"
                aria-label="Toggle navigation"
            >
                <i class="fas fa-bars"></i>
            </button>

            <div class="collapse navbar-collapse" id="navbarResponsive">
                <ul class="navbar-nav ms-auto py-4 py-lg-0">
                    <li class="nav-item">
                        <RouterLink to="/" class="nav-link px-lg-3 py-3 py-lg-4"
                        style="color: white;"
                            >Home</RouterLink
                        >
                    </li>
                    <li class="nav-item">
                        <RouterLink
                            to="/movie"
                            class="nav-link px-lg-3 py-3 py-lg-4"
                            style="color: white;"
                            >Movie</RouterLink
                        >
                    </li>

                    
                </ul>
            </div>
        </div>
    </nav>
</template>

<style scoped>

nav{
 background-color: #a70000;
 /* background-color: transparent; */
}

h1{
    color: white;
}

</style>

