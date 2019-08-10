<template>
    <div id="product-card" class="base-layout">
        <h1>Products</h1>
        <div id="products-area" :style="{transform:'translateX(' + slide_move_x +'%)'}">
        
            <ul>
                <li
                class="product-item"
                v-for="(product, prod_i) in products_exhib"
                :key="prod_i"
                >
                <a :href="product.app_url">
                <div class="product-link">
                <p class="title">{{product.name}}</p>
                <p class="data">{{product.data}}</p>
                <p class="language">{{product.main_tech}}</p>
                <img :src="product.img_url">
                </div>
                </a>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            product_num : 0,
            products:[
                {//ポートフォリオサイト
                    name:"My portfolio",
                    data:"2019.8",
                    main_tech:"vue.js",
                    img_url:"/img/portfolio.PNG",
                    app_url:"http://localhost:8080/"
                },
                {//分室のフレッシャーズキャンプアンケート
                    name: "FCQuestionnaire",
                    data:"2018/1 ~ 2018/3",
                    main_tech: "node.js",
                    img_url:"img/FCQuestionnaire.PNG",
                    app_url:"http://www.comm.tcu.ac.jp/bunsitu/FCQuestionnaire/"
                },
                {//分室ホームページ
                    name:"bunsitsuHP",
                    data:"2018/10 ~ 2018/12",
                    main_tech:"HTML5,CSS,JS,JQuery",
                    img_url:"/img/bunsitsuHP.PNG",
                    app_url:"http://www.comm.tcu.ac.jp/bunsitu/"
                },
                {//アウトベーダ―
                    name:"outvader",
                    data:"2019/5",
                    main_tech:"C,DxLib",
                    img_url:"/img/Outvader.png",
                    app_url:""

                }
            ],
            // 画面上に映し出されるproducts
            products_exhib:[],
            //今現在，画面上に表示されているproductsの番号
            product_exhib_num:0,
            slide_move_x : -25,//スライドの移動量
            animation_interval : null
        }
    },
    methods:{
        //今現在，画面上に表示されているproductの番号を指定の番号に更新する
        allocateProductExhibNum:function(new_exhibit_num){
            this.products_exhib = [];

            //指定の左側のproductを決める際に0を下回らないように
            //0を下回った場合にはproducts[length-1]に差し替え
            this.products_exhib[0] = 
                (new_exhibit_num - 1 < 0)? this.products[this.products.length-1] : this.products[new_exhibit_num -1];

            this.products_exhib[1] = this.products[new_exhibit_num];

            for(let product_i = 1; product_i<=2; product_i++){
                //指定の右側のproductを決める際にproducts.length-1を上回らないように
                //products.length-1を上回った場合には0からの連番に差し替え
                this.products_exhib[product_i + 1] = 
                    (new_exhibit_num + product_i < this.products.length) ? this.products[new_exhibit_num+product_i] : this.products[(new_exhibit_num+product_i) % this.products.length];
            }
        },
        addProductNumber: function(){
            this.product_exhib_num++;
            if(this.product_exhib_num > this.products.length - 1)this.product_exhib_num = 0;
            this.allocateProductExhibNum(this.product_exhib_num);
        },
        animateSlide:function(){
            this.slide_move_x-= 0.1;
             if(this.slide_move_x <= -48){
                this.addProductNumber();
                this.slide_move_x = -24;
                
            }
        }
    },
    computed:{
        Initialize:function(){
            this.allocateProductExhibNum(this.product_exhib_num)
            setInterval(this.animateSlide,1000);
        },
        changeProductTimeout : function(){
            setInterval()
        }
    },
    mounted:function(){
        this.allocateProductExhibNum(this.product_exhib_num);
        this.animation_interval = setInterval(this.animateSlide,30);
    },
    beforeDestroy:function(){
        clearInterval(this.animation_interval);

    }
}
</script>

<style>
    #product-card #products-area{
        height:60vh;
        width:320%;
        text-align: center;
    }

    #product-card #products-area ul{
        width:100%;
        height:inherit;
        margin:0;
        overflow: hidden;    
    }

    #product-card #products-area ul li.product-item{
        width:22%;
        height: inherit;
        float:left;
        overflow: hidden;
        list-style: none;
        border:solid 1px #2e2e2e;
        height:99%;
        margin:0 1%;
        box-shadow: 5px 5px 5px #2e2e2e;
    }

    #product-card #products-area ul li.product-item a{
        text-decoration: none;
        color:#2e2e2e;
    }

    #product-card #products-area ul li.product-item a .product-link{
        width:100%;
        height:100%;
    }

    #product-card #products-area ul li.product-item .product-link p{
        width:100%;
        text-align:left;
        text-decoration: none;
        margin:5px;
        padding:0 0 0 10px;
    }

    #product-card #products-area ul li.product-item .product-link p.title{
        font-size:32px;
    }
    #product-card #products-area ul li.product-item .product-link p.data{
        padding-left:30px;
    }
    #product-card #products-area ul li.product-item .product-link p.language{
        padding-left:30px;
    }

    #product-card #products-area ul li.product-item  .product-link img{
        width:60%;
        border:solid 1px #2e2e2e;
    }


</style>
