<template>
    <div class="header-container">
        <div class="nav">
          <a href="/"><img src="@/components/img/logo.jpg" class="brand-logo" alt=""></a>
          <div class="nav-items">
            <div class="nav-item">
              <router-link to="/login">
                <img src="@/components/img/profil.webp" alt="">
              </router-link>
              <router-link to="/cart">
                <img src="@/components/img/basket.jpg" alt="">
              </router-link>
            </div>
          </div>
        </div>
      </div>
          <ul class="links-container">
            <li><router-link to="/" class="routers-link">Home</router-link></li>
            <li><router-link to="/product" class="routers-link">All</router-link></li>
            <li><router-link to="/Women" class="routers-link">Women</router-link></li>
            <li><router-link to="/kids" class="routers-link">Kids</router-link></li>
          </ul>
          <div class="first-products">
          <div class="prod1">
          <section class="product-details1">
            <div class="image-slider1">
                <div class="product-images">
                </div>
            </div>
        </section>  
        <div class="product-info">
            <h1>adidas SOULSTRIDE FLOW GTX SHOES</h1>
            <div class="price">$89.00</div>
            <p>Men</p>
            <!-- Autres informations sur le produit -->
            <div class="size">
                <label for="age">Size :</label>
                <input type="number" id="size"/>
            </div>
            <button type="submit" class="submit-button">BUY NOW</button>
            <button type="submit" class="bag">ADD TO BAG</button>
        </div>
    </div>  
    <div class="prod5">
        <section class="product-details5">
            <div class="image-slider5">
                <div class="product-images">
                </div>
            </div>
        </section>
        <div class="product-info5">
            <h1>ASICS GEL CUMULUS 23</h1>
            <div class="price">$75.40</div>
            <p>Men</p>
            <!-- Autres informations sur le produit -->
            <div class="size">
                <label for="age">Size :</label>
                <input type="number" id="size" min="39" max="48"/>
            </div>
            <button type="submit" class="submit-button">BUY NOW</button>
            <button type="submit" class="bag">ADD TO BAG</button>
        </div>
    </div> 
    </div>
    <footer>
        <div class="footer-container">
          <img src="@/components/img/nike.jpg" alt="Nike" class="nike" style="width: 20%; height: auto; ">
          <a href="https://www.instagram.com/efrei_tennis_de_table" class="instagram-link">
            <img src="https://www.unipile.com/wp-content/uploads/2022/09/logo_instagram.png" alt="Instagram" class="instagram" style="width: 15%; height: auto; justify content: center"/></a>
          <img src="https://cdn.britannica.com/94/193794-050-0FB7060D/Adidas-logo.jpg" alt="Adidas" class="Adidas" style="width: 20%; height: auto; ">
        </div>
        <p class="footer-title">about company</p>
        <p class="info">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Repellat tempore ad suscipit, eos eius quisquam sed optio nisi quaerat fugiat ratione et vero maxime praesentium, architecto minima reiciendis iste quo deserunt assumenda alias ducimus. Ullam odit maxime id voluptates rerum tenetur corporis laboriosam! Cum error ipsum laborum tempore in rerum necessitatibus nostrum nobis modi! Debitis adipisci illum nemo aperiam sed, et accusamus ut officiis. Laborum illo exercitationem quo culpa reprehenderit excepturi distinctio tempore cupiditate praesentium nisi ut iusto, assumenda perferendis facilis voluptas autem fuga sunt ab debitis voluptatum harum eum. Asperiores, natus! Est deserunt incidunt quasi placeat omnis, itaque harum?</p>
        <p class="info">support emails - help@shoeshop.com, customersupport@shoeshop.com</p>
        <p class="info">telephone - 180 00 00 001, 180 00 00 002</p>
        <p class="footer-credit">ShoeShop, Best Shoes online store</p>
      </footer>
</template>
<script>
import '@/components/script.css';
import axios from 'axios';

export default {
    name: 'MenProducts',
    data() {
    return {
        responseData: {
            message: '',
            data: { items: [] },
        },
    };
},
mounted() {
    // Make an Axios GET request to your backend endpoint
    axios.get('http://localhost:8080/men')
        .then((response) => {
            // Assign the response data to the responseData property
            this.responseData = response.data;
        }).
        catch((error) => {
            console.error('Error fetching data:', error);
        });
    },
}
</script>
<style scoped>
.first-products{
    display: flex;
    justify-content: space-around; /* Ajustez selon vos besoins */
    margin-left: 10px;
}
.product-details1{
    width: 100%;
    padding: 60px 10vw;
    display: flex;
    justify-content: space-between;
}

.image-slider1{
    width: 540px ;
    height: 300px;
    position: relative;
    background-image: url('@/components/img/adidas2.jpg');
    background-size: cover;
    left: -200px;
    margin-bottom: -50px;
}
.prod1{
    margin-left:50px;
}
.prod5{
    margin-left: -600px;
}
.image-slider5{
    width: 540px ;
    height: 380px;
    position: relative;
    background-image: url('https://images.asics.com/is/image/asics/1011B012_410_SR_RT_GLB?$zoom$');
    background-size: cover;
    left: 00px;
    margin-bottom: -50px;
}
.product-info {
    max-width: 500px; /* Ajustez la largeur maximale selon vos besoins */
    text-align: center; /* Centrez le contenu horizontalement */
    margin-right: 425px;
}

.product-info h1 {
    text-transform: uppercase; /* Met la marque en majuscules */
    margin-bottom: 5px; /* Ajoute un espace en bas */
    font-size:14px;
}

.product-info .price {
    font-weight: bold; /* Met le prix en gras */
    font-size: 1.2em; /* Ajustez la taille de la police du prix selon vos besoins */
}

.size{
    justify-content: center;
    color: black; /* Couleur du texte de l'étiquette de taille */
    padding: 10px 20px; /* Rembourrage de l'étiquette de taille */
    font-size: 16px; /* Taille de la police de l'étiquette de taille */
    border: none; /* Supprimer la bordure de l'étiquette de taille */
    border-radius: 5px; /* Arrondi des bords de l'étiquette de taille */
    cursor: pointer;
}

.bag{
    margin-top: 5px;
    background-color: rgb(214, 19, 32);
    color: black; 
    padding: 10px 40px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    text-transform: uppercase;
    font-weight: bold;
    margin-left: 10px; 
}
.bag:hover{
    background-color: rgb(255, 5, 50);
}

.product-info5 {
    max-width: 350px; /* Ajustez la largeur maximale selon vos besoins */
    text-align: center; /* Centrez le contenu horizontalement */
    margin-top: 50px;
    margin-left: 100px;
}

.product-info5 h1 {
    text-transform: uppercase; /* Met la marque en majuscules */
    margin-bottom: 5px; /* Ajoute un espace en bas */
    font-size:14px;
}

.product-info5 .price {
    font-weight: bold; /* Met le prix en gras */
    font-size: 1.2em; /* Ajustez la taille de la police du prix selon vos besoins */
}
</style>