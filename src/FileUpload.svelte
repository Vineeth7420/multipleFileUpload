<script>
    export let multiple = true;

    let files = [];
    function handleChange(e){
        console.log(e)
        
       files =  [...files, ...e.target.files]

       console.log(files)
    }

    
   

</script>
<input type="file" multiple= {multiple} on:change={handleChange} />
    <p>Select the Files</p>

    <table class = 'center'>

        <thead>
            <tr>
                <th class="space">Name</th>
                <th class="space1">Size</th>
                <th>Type</th>
            </tr>
        </thead>
        <tbody>
            {#each files as f, i (i)}
            <tr>
                <td class="space-down">{f.name}</td>
                <td class="space-down">{f.size}</td>
                <td class="space-down">{f.type}</td>
            </tr>
            {/each}
            
        </tbody>
    </table>

<button>Submit</button>

<style>
    .center{
        margin-left: auto;
        margin-right: auto;
    }

    .space, .space1{
        padding-right: 25px;
    }

    .space-down{
        padding-right: 25px;
    }

    button{
        margin-top: 50px;
    }


</style>