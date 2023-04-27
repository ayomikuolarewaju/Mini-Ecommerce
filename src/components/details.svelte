<script>
    import img1 from '../img/rem.svg';
    import {store} from '../components/stores'
    let prices = $store.map((p)=> p[0].price)
    let total = prices.reduce((n,m)=>n+m,0)
    
     const decrefruit =(id)=>{
        let newP = $store.filter((p)=> p[0].id !== id)
        if($store.length === 0){
            return
        }else{
            $store = newP;
            prices = $store.map((p)=> p[0].price)
            total = prices.reduce((n,m)=>n+m,0)
        }
    }
    
</script>

{#each $store as pd }
    <div class="container items-center mx-auto text-center w-full">
        <div class="flex flex-row justify-between p-5 capitalize w-2/3 mx-auto">
            <img src="{pd[0].img}" alt="" srcset="" width="45" height="45">
            <p>{pd[0].name}</p>
            <p>₦{pd[0].price}</p>
            <img src="{img1}" alt="" width="25" height="25" on:click={()=>decrefruit(pd[0].id)} on:keydown>
        </div>
    </div>
{/each}
<div class="flex flex-row container p-10 justify-between w-2/3 mx-auto">
    <h4><strong>Total</strong></h4>
    <p><strong>₦{total}</strong></p>
 </div>