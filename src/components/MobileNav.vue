<template>
    <div>
        <div class="mobile-navbar">
            <h2>Blogr</h2>
        </div>
        <div class="menu-box" @click="openSidebar" :class="{ 'active-sidebar' : active_sidebar }">
            <div class="hamb-menu"></div>
            <div class="sidebar" @click.stop>
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
        }
    },
    methods: {
        openSidebar(){
            if(this.active_sidebar === false){
                this.active_sidebar = true;
            }else {
                this.active_sidebar = false;
            }
        },

        activeSublist(event){
            let submeni = event.target.nextSibling;
            let height = 0;
            let current_height = submeni.offsetHeight;
            let delay = 100;
            let all = document.getElementsByClassName("sublist");
            for (let i = 0; i < all.length; i++) {
                all[i].style.height = height;
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

        }
    },
}
</script>