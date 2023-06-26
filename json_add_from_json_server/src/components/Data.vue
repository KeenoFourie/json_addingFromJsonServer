<template>
    <div id="full">
        <div id="display">

        </div>
    </div>
</template>

<script>

async function getData() {
    let data = await fetch("https://keenofourie.github.io/json-server/index.json")
    let chocolateData = await data.json()

    data_for_chocolates = chocolateData.chocolate

    let display = document.querySelector("#display")
    
    data_for_chocolates.forEach(chocolate => {
        display.innerHTML +=`
        <div id="cards" class="card" style="width: 18rem;">
        <div class="card-body">
            <h4 class="card-title" id="heading">${chocolate.brand}</h4>
            <h6 class="card-title" id="price">${chocolate.price}</h6>
        </div>
        </div>
        `
    })
}
getData()
</script>

<style>
#display {
    display: flex;
    flex-wrap: wrap;
    margin: 2rem;
    margin-top: 2rem;
    padding: 1rem;
    text-align: center;
    justify-content: space-evenly;
}
#cards {
    box-shadow: 0px 0px 25px black;
    margin: 5rem;
}
#heading {
    font-family: cursive;
    font-weight: bold;
}
#price {
    color: red;
}
</style>