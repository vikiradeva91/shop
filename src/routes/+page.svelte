<script>
  import data from "../json/products.json";
  import { cart, alert } from "../store";

  let sorting = "Sort";
  let products = data;

  let page = 1;
  let filtered = [...products];
  filtered.length = 8;

  let category = "all";

  let showFilter = false;

  function handleCategory(cat) {
    filtered = products.filter((item) => item.category == cat);
    category = cat;
    console.log(filtered);
  }

  function handelMore() {
    page++;
    filtered = [...products];
    if (page * 8 < data.length) {
      filtered.length = page * 8;
    } else {
      filtered.length = data.length;
    }
  }

  function handelSort() {
    if (sorting == "Price ascending") {
      filtered.sort((a, b) => a.price - b.price);
    }

    if (sorting == "Price descending") {
      filtered.sort((a, b) => a.price - b.price).reverse();
    }

    if (sorting == "Alphabetical a-z") {
      filtered.sort((a, b) => a.name.localeCompare(b.name));
    }

    if (sorting == "Alphabetical z-a") {
      filtered.sort((a, b) => a.name.localeCompare(b.name)).reverse();
    }
    filtered = filtered;
  }

  function handelColorSelect(color) {
    filtered = data;
    filtered = products.filter((item) => item.color == color);
  }

  function handelColorReset() {
    filtered = data;
  }

  function handelCategoryReset() {
    filtered = data;
    category = "all";
  }

  function handleAddToCart() {
    $cart++;
    $alert = "Item added to cart.";
    setTimeout(() => {
      $alert = "";
    }, "3000");
  }
</script>

<!-- NAVBAR -->

<div class="container">
  <div id="navbar">
    <div class="flex-navbar">
      <div class="description">
        <h1>{category.toUpperCase()}</h1>
        <span>{filtered.length} Products</span>
      </div>
      <div class="sort-settings">
        <select
          name="Sort"
          id="sort"
          bind:value={sorting}
          on:change={handelSort}
        >
          <option value="Sort">Sort</option>
          <option value="Alphabetical a-z">Alphabetical a-z</option>
          <option value="Alphabetical z-a">Alphabetical z-a</option>
          <option value="Price ascending">Price ascending</option>
          <option value="Price descending">Price descending</option>
        </select>
      </div>
    </div>
  </div>

  <!-- NAVAR END -->

  <!-- MAIN -->

  <div id="main">
    <section class="d-flex">
      {#each filtered as item}
        <div class="page-wrapper">
          <div class="page-inner">
            <div class="el-wrapper">
              <div class="box-up">
                <img class="img" src="/img/{item.image}" alt="light-1" />
                <div class="img-info">
                  <div class="info-inner">
                    <span class="p-name">{item.name}</span>
                  </div>
                  <div class="a-size">
                    Categories :<span class="size">{item.category}</span>
                  </div>
                </div>
              </div>

              <div class="box-down">
                <div class="h-bg">
                  <div class="h-bg-inner" />
                </div>

                <a class="cart" href="/">
                  {#if item["old-price"]}
                    <span class="old-price">${item["old-price"]}</span>
                    <span class="new-price">${item.price}</span>
                  {:else}
                    <span class="price">${item.price}</span>
                  {/if}

                  <span class="add-to-cart">
                    <span on:click|preventDefault={handleAddToCart} class="txt"
                      >Add to cart</span
                    >
                  </span>
                  <span class="heart"
                    ><picture><img src="/svg/heart.svg" alt="" /></picture
                    ></span
                  >
                </a>
              </div>
            </div>
          </div>
        </div>
      {/each}
    </section>
    {#if filtered.length < data.length}
      <div style="text-align: center; margin-top: 20px;">
        <a href="/" on:click|preventDefault={handelMore} class="button-more"
          >Load More</a
        >
      </div>
    {/if}
  </div>

  <!-- MAIN END -->

  <!-- SIDEBAR -->
  <div id="sidebar">
    <div>
      <a href="/" on:click={() => (showFilter = true)} class="filter-btn"
        ><span>Filter</span></a
      >
    </div>
    <section id="filter" class:show={showFilter}>
      <div class="ui-group">
        <div class="flex">
          <input id="category" type="checkbox" />
          <label id="category-label" for="category">Category</label>
          <span class="closebtn inverse" on:click={() => (showFilter = false)}
            >&times;</span
          >
        </div>

        <div
          id="category-button-group"
          class="button-group js-radio-button-group"
          data-filter-group="category"
        >
          <div>
            <input type="checkbox" value="*" id="all" />
            <label
              on:click={handelCategoryReset}
              class="button is-checked"
              for="all">All</label
            >
          </div>
          <div>
            <input type="checkbox" value=".new" id="new" />
            <label
              on:click={() => handleCategory("applications")}
              class="button"
              for="new">Applications</label
            >
          </div>
          <div>
            <input type="checkbox" value=".women" id="women" />
            <label
              on:click={() => handleCategory("lanterns")}
              class="button"
              for="women">Lanterns</label
            >
          </div>
          <div>
            <input type="checkbox" value=".men" id="men" />
            <label
              on:click={() => handleCategory("chandeliers")}
              class="button"
              for="men">Chandeliers</label
            >
          </div>
          <div>
            <input type="checkbox" value=".men" id="men" />
            <label
              on:click={() => handleCategory("table-lamps")}
              class="button"
              for="men">Table Lamps</label
            >
          </div>
        </div>
      </div>

      <div class="ui-group">
        <div class="flex">
          <input id="color" type="checkbox" />
          <label id="color-label" for="color">Color </label><a
            class="reset"
            href="/"
            on:click={handelColorReset}>Reset</a
          >
        </div>

        <div
          id="color-button-group"
          class="button-group js-radio-button-group"
          data-filter-group="color"
        >
          <div
            on:click={() => handelColorSelect("white")}
            id="white"
            class="color-circle button"
          />
          <div
            on:click={() => handelColorSelect("yellow")}
            id="yellow"
            class="color-circle button"
          />
          <div
            on:click={() => handelColorSelect("brown")}
            id="brown"
            class="color-circle button"
          />
          <div
            on:click={() => handelColorSelect("black")}
            id="black"
            class="color-circle button"
          />
        </div>
      </div>

      <div class="filter-content show" id="collapse_3">
        <div class="ui-group card-body">
          <input id="price" type="checkbox" />
          <label id="price-label" for="price">Price</label>
          <div class="form-row button-group">
            <input
              type="range"
              class="custom-range"
              min="0"
              max="100"
              name=""
            />
            <div>
              <div class="form-group col-md-6">
                <label for="min">Min</label>
                <input class="form-control" placeholder="$0" type="number" />
              </div>
              <div class="form-group text-right col-md-6">
                <label for="max">Max</label>
                <input
                  class="form-control"
                  placeholder="$1,0000"
                  type="number"
                />
              </div>
            </div>
            <a href="/" class="button" style="margin-bottom: 30px">Apply</a>
          </div>
        </div>
      </div>
    </section>
  </div>
</div>

<!-- SIDEBAR END -->
