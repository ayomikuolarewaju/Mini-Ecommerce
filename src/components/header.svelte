<script>
    import img from '../img/logo.jpg'
    import cart from '../img/cart.svg'
    import {store} from '../components/stores'
    import { goto } from '$app/navigation';
</script>


<div class="flex flex-row bg-gray-600 text-white h-20 items-start mb-5">
    <div class="container flex flex-row justify-between p-5">
        <div class="flex flex-row space-x-4 hover:cursor-pointer">
            <img src="{img}" alt="" srcset="" width="55" height="15" on:click={()=>goto('/')} on:keydown>
        </div>
        <div class="flex flex-row space-x-4 hover:cursor-pointer">
            <img src="{cart}" alt="" srcset="" width="35" height="35" on:click={()=>goto('/detailCart')} on:keydown>
            <p>{$store.length}</p>
        </div>
    </div>
</div>