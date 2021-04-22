<template>
    <div>
        <div class="mobile-navbar">
            <h2>Blogr</h2>
        </div>
         <div class="menu-box" @click="openSidebar" :class="{ 'active-sidebar' : active_sidebar }">
            <div class="hamb-menu"></div>
            <div class="sidebar" @click.stop :style="{ height : height+'px' }">
                <ul class="mainlist">
                    <li>
                        <p>Product</p> 
                        <ul class="sublist">
                            <li>Overview</li>
                            <li>Pricing</li>
                            <li>Marketing</li>
                            <li>Features</li>
                            <li>Integrations</li>
                        </ul>
                    </li>

                    <li>
                        <p>Company</p> 
                        <ul class="sublist">
                            <li>About</li>
                            <li>Team</li>
                            <li>Blog</li>
                            <li>Careers</li>
                        </ul>
                    </li>

                    <li>
                        <p>Connect</p>
                        <ul class="sublist"> 
                            <li>contakt</li>
                            <li>Newsletter</li>
                            <li>LinkedIn</li>
                        </ul>
                    </li>
                </ul>
            </div>
        </div>
    </div>    
</template>

<script>
export default {
    data() {
        return {
            active_sidebar: false,
            height: 0,
        }
    },

    methods: {
        openSidebar(){
            let mainlist = document.getElementsByClassName('mainlist')[0];

            if(this.active_sidebar === false) {
                this.active_sidebar = true;
                this.height = mainlist.offsetHeight;
            }else {
                this.active_sidebar = false;
                this.height = 0;
            }

            


            //RIJEŠENJE BROJ 2
            //let height = 0;
            //dohvati sidebar preko klase, pošto je jedan jedini sidebar onda stavljamo [0] jer nam dohvacanje preko klase vraća array jer očekuje da će biti više elemenata[]
            //let sidebar = document.getElementsByClassName('sidebar')[0];
            //dodaj stil height na upravno dohvaćeni sidebar
            //sidebar.style.height = height + 'px';
        }
    },
}
</script>