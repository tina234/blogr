<template>
    <div>
        <div class="mobile-navbar">
            <h2>Blogr</h2>
        </div>
         <div class="menu-box" @click="openSidebar" :class="{ 'active-sidebar' : active_sidebar }">
            <div class="hamb-menu"></div>
            <div class="sidebar" @click.stop :style="{ height : height + 'px' }">
                <ul class="mainlist">
                    <li>
                        <p @click="activeSublist($event)">Product</p> 
                        <ul class="sublist">
                            <li>Overview</li>
                            <li>Pricing</li>
                            <li>Marketing</li>
                            <li>Features</li>
                            <li>Integrations</li>
                        </ul>
                    </li>

                    <li>
                        <p @click="activeSublist($event)">Company</p> 
                        <ul class="sublist">
                            <li>About</li>
                            <li>Team</li>
                            <li>Blog</li>
                            <li>Careers</li>
                        </ul>
                    </li>

                    <li>
                        <p @click="activeSublist($event)">Connect</p>
                        <ul class="sublist"> 
                            <li>Contact</li>
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
            let delay = 100;

            if(this.active_sidebar === false) {
                this.active_sidebar = true;
                this.height = mainlist.offsetHeight;
                mainlist.childNodes.forEach(element => {
                    setTimeout(() => {
                       element.style.opacity = 1;
                       element.style.transform = "translateY(0%)";
                    }, delay += 150);
                });

            }else {
                this.active_sidebar = false;
                this.height = 0;
                 mainlist.childNodes.forEach(element => {
                    element.style.opacity = "";
                    element.style.transform = "";
                });
            }

            //RIJEŠENJE BROJ 2
            //let height = 0;
            //dohvati sidebar preko klase, pošto je jedan jedini sidebar onda stavljamo [0] jer nam dohvacanje preko klase vraća array jer očekuje da će biti više elemenata[]
            //let sidebar = document.getElementsByClassName('sidebar')[0];
            //dodaj stil height na upravno dohvaćeni sidebar
            //sidebar.style.height = height + 'px';
        },

        activeSublist(event){
            let submeni = event.target.nextSibling; /*na klik targeta recimo "product" pokazi njegove siblingse tj njegovu listu*/
            let height = 0;
            let current_height = submeni.offsetHeight;
            let delay = 100;
            let all = document.getElementsByClassName("sublist");
            for (let i = 0; i < all.length; i++) {
                if(all[i].style.height){
                    this.height -= all[i].style.height.split('px')[0];
                }
                all[i].style.height = '';
            }

            if(current_height < 1){
                submeni.childNodes.forEach(element => {
                    height += element.offsetHeight;
                    setTimeout(() => {
                       element.style.opacity = 1;
                    }, delay += 150);
                });
            }
            submeni.style.height = height + 'px';
            this.height += height;
        }
    },    
}
</script>