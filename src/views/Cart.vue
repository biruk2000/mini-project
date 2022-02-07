<template>
  <div>
    <div class="shopping-cart">
      <!-- Title -->

      <div class="column-labels">
        <label class="image">Product</label>
        <label class="description-col">Description</label>
        <label class="quantity-col">Quantity</label>
        <label class="price-col">Price</label>
        <label class="buttons-col">Remove</label>
      </div>

      <!-- Product #1 -->
      <div class="item" v-for="it in items" :key="it.id">
        <div class="image">
          <img src="../assets/logo.png" alt="" />
        </div>

        <div class="description">
          <span>{{i.productName}}</span>
        </div>

        <div class="quantity">
          <input type="number" name="name" v-model="i.quantity" @change="calculateTotal"  min="1" />
        </div>

        <div class="price">N{{i.price}}</div>

        <div class="buttons" @click="removeItem(i)">
          <span>{{it.productName}}</span>
        </div>

        <div class="quantity">
          <input type="number" name="name" v-model="it.quantity" @change="calculateTotal"  min="1" />
        </div>

        <div class="price">N{{it.price}}</div>

        <div class="buttons" @click="removeItem(it)">
          <span class="delete-btn">X</span>
        </div>
      </div>
      <div class="total">
        <label>Total:</label>
        <div class="totals-value">N{{totalPrice}}</div>
      </div>
      <div class="payment">
        <p>*Please use the following test credit card for payments <br>
        42424242424242 -Exp:01/20 - 123</p>
      </div>
      <div class="pay">
        <a href="">pay now</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'cart',
  data(){
    return{      
      totalPrice: 0,
      items: [
        {
          id: 1,
          productName: 'First Product',
          image: '../assets/logo.png',
          quantity: 1,
          price: 23
        },
        {
          id: 2,
          productName: 'Second Product',
          image: '../assets/logo.png',
          quantity: 1,
          price: 23
        },
        {
          id: 3,
          productName: 'Third Product',
          image: '../assets/logo.png',
          quantity: 1,
          price: 23
        }
      ]
    }
  },

  methods: {
   calculateTotal(){
     let total = 0;
     for(let i=0; i<this.items.length; i++){
      total += this.items[i].price * this.items[i].quantity
     }
     this.totalPrice = total
   },
   removeItem(it){
     const index = this.items.findIndex(it => it.id === it.id);
     this.items.splice(index,1);
     this.calculateTotal();
   }
  },
  created(){
    this.calculateTotal();
  }
};
</script>

<style scoped>
/* table column styles */

.shopping-cart {
  width: 750px;
  height: 423px;
  margin: 60px auto;
  display: flex;
  flex-direction: column;
}

.column-labels {
  display: flex;
  padding: 20px 30px;
  border-bottom: 1px solid #969696;
  font-size: 18px;
  font-weight: 300;
  text-align: center;
}

.column-labels label {
  padding-right: 40px;
  color: #919191;
}

.description-col,
.quantity-col,
.price-col,
.buttons-col {
  margin-right: 40px;
}

/* .column-labels label{
  margin-right: 10px;
} */

.item {
  padding: 20px 30px;
  height: 120px;
  display: flex;
}

.item:last-of-type {
  border-bottom: 1px solid #919191;
}

.buttons {
  position: relative;
  padding-top: 30px;
  margin-left: 120px;
}

.delete-btn {
  display: inline-block;
  font-weight: bold;
  cursor: pointer;
}

.delete-btn {
  width: 18px;
  height: 17px;
  background-repeat: no-repeat;
  text-align: center;
}

.image {
  margin-right: 50px;
}

.image img {
  width: 100px;
}

.description {
  padding-top: 10px;
  margin-top: 20px;
  margin-right: 60px;
  width: 115px;
}

.description span {
  display: block;
  font-size: 14px;
  color: #919191;
  font-weight: 400;
  text-align: center;
}

.quantity {
  margin-top: 20px;
  margin-right: 60px;
}
.quantity input {
  width: 32px;
  font-size: 16px;
  border: 2px solid rgb(86, 231, 171);
  font-weight: 300;
}

.price {
  width: 83px;
  padding-top: 27px;
  text-align: center;
  font-size: 16px;
  color: #919191;
  font-weight: 300;
}

.total {
  text-align: end;
  padding-right: 60px;
  
  text-transform: uppercase;
  font-size: 1.4rem;

}
.total div{
  display: inline-block;
  margin-top: 20px;
}

.payment{
  margin-top: 10px;
  text-align: end;
  padding-right: 90px;
  color: red;
  font-size: 1.2rem;
}

.pay{
  text-align: end;
  padding-right: 40px;
}
.pay a{
  text-decoration: none;
  background-color: rgb(0, 180, 156);
  color: #fff;
  border: none;
  padding: 5px 15px;
  text-align: center;
  display: inline-block;
  font-size: 16px;
  border-radius: 2px;
}



@media screen and (max-width: 650px) {
  .column-labels {
    display: none;
  }
}

@media (max-width: 650px) {
  .shopping-cart {
    width: 100%;
    height: auto;
    overflow: hidden;
  }

  .item {
    height: auto;
    flex-wrap: wrap;
    justify-content: center;
  }

  .image img {
    width: 50%;
  }

  .image,
  .quantity,
  .description {
    width: 100%;
    text-align: center;
    margin: 6px 0;
  }
}
</style>
