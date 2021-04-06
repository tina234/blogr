<template>
    <div class="header-cont">
        <img src="../assets/bg-pattern-intro.png" alt="">
        <div class="nav-bar">
            <h2>Blogr</h2>
            <div class="navbar-items">
                <div class="nav-left">
                    <div class="menu-item">
                        <span>Product</span>
                        <i class="fa fa-caret-down" aria-hidden="true"></i>

                        <div class="dropdown-list">
                            <div class="drop-item">Overview</div>
                            <div class="drop-item">Marketplace</div>
                            <div class="drop-item">Pricing</div>
                            <div class="drop-item">Freatures</div>
                            <div class="drop-item">Integrations</div>
                        </div>
                    </div>
                    <div class="menu-item">
                        <span>Company</span>
                        <i class="fa fa-caret-down" aria-hidden="true"></i>

                        <div class="dropdown-list">
                            <div class="drop-item">About</div>
                            <div class="drop-item">Team</div>
                            <div class="drop-item">Blog</div>
                            <div class="drop-item">Careers</div>
                        </div>
                    </div>
                    <div class="menu-item">
                        <span>Connect</span>
                        <i class="fa fa-caret-down" aria-hidden="true"></i>

                        <div class="dropdown-list">
                            <div class="drop-item">Contact</div>
                            <div class="drop-item">Newsletter</div>
                            <div class="drop-item">LInkedIn</div>
                        </div>
                    </div>
                </div>
                <div class="nav-right">
                    <p>Login</p>
                    <button class="btn-sign-in">Sign in</button>
                </div>
            </div>
        </div>

        <div class="main-title">
            <h1>A modern publishing platform</h1>
            <p>Grow your audience and built your own brand</p>
            <div>
                <button class="btn-start">Start for free</button>
                <button class="btn-more">Learn more</button>
            </div>
        </div>    
    </div>
</template>

<script>
    export default {
    }
</script>


<style lang="scss">
    @import "../scss/header.scss";
</style>
