<script>
    import Header from '../components/header.svelte';
    import {store } from '../components/stores'
    import add from '../img/add 2.svg'
    import minus from '../img/minus.svg'
    export let data;
    const products = data.product
    const increfruit =(id)=>{
        let newP = products.filter((p)=> p.id === id)
        $store = [...$store,newP]
    }
    const decrefruit =(id)=>{
        let newP = $store.filter((p)=> p[0].id !== id)
        if($store.length === 0){
            return
        }else{
            $store = newP
        }
    }
</script>

<div >
    <Header/>

<div class="flex flex-col bg-gray-300 text-white mx-auto items-center">
        <div class="flex flex-col space-y-5 container">
          {#each products as product (product.id)}
             <div class="flex flex-row justify-between my-2 p-5 bg-slate-500 rounded-md shadow-lg capitalize">
              <img src="{product.img}" alt="" srcset="" width="50" height="50">
              <h4 >{product.name}</h4>
              <h5>₦{product.price}</h5>
              <p>{product.des}</p>
              <div class="space-x-7">
                <button on:click={()=>increfruit(product.id)}><img src="{add}" alt="" width="20" height="20"></button>
                <button on:click={()=>decrefruit(product.id)}><img src="{minus}" alt="" width="20" height="20"></button>
              </div>
             </div>
          {/each}
        </div>
</div>
</div>
