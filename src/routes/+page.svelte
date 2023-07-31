<div class="container">
  <div id="navbar">
    <div class="flex-navbar">
      <div class="description">
        <h1>Products</h1>
        <span>1,872 Products</span>
      </div>
      <div class="sort-settings">
        <select name="Sort" id="sort">
          <option value="Sort">Sort</option>
          <option value="Relevance">Relevance</option>
          <option value="New in">New in</option>
          <option value="Price (low-high)">Price (low-high)</option>
          <option value="Price (high-low)">Price (high-low)</option>
          <option value="Brand (A-Z)">Brand (A-Z)</option>
          <option value="Brand (Z-A)">Brand (Z-A)</option>
        </select>
      </div>
    </div>
  </div>
  <div id="main">Main</div>
  <div id="sidebar">
    <div>
      <a href="/" class="filter-btn"><span>Filter</span></a>
    </div>
    <section id="filter">
      <div class="ui-group">
        <input id="category" type="checkbox" />
        <label id="category-label" for="category"
          ><i class="down fa fa-caret-down" aria-hidden="true" />Category</label
        >
        <div
          id="category-button-group"
          class="button-group js-radio-button-group"
          data-filter-group="category"
        >
          <div>
            <input type="checkbox" value="*" id="all" />
            <label class="button is-checked" for="all">All</label>
          </div>
          <div>
            <input type="checkbox" value=".new" id="new" />
            <label class="button" for="new">New Arrivals</label>
          </div>
          <div>
            <input type="checkbox" value=".women" id="women" />
            <label class="button" for="women">Women</label>
          </div>
          <div>
            <input type="checkbox" value=".men" id="men" />
            <label class="button" for="men">Men</label>
          </div>
        </div>
      </div>

      <div class="ui-group">
        <input id="color" type="checkbox" />
        <label id="color-label" for="color"
          ><i class="down fa fa-caret-down" aria-hidden="true" />
          Color</label
        >
        <div
          id="color-button-group"
          class="button-group js-radio-button-group"
          data-filter-group="color"
        >
          <div id="grey" class="color-circle button" data-filter=".grey" />
          <div id="red" class="color-circle button" data-filter=".red" />
          <div id="green" class="color-circle button" data-filter=".green" />
          <div id="yellow" class="color-circle button" data-filter=".yellow" />
          <div id="blue" class="color-circle button" data-filter=".blue" />
          <div id="purple" class="color-circle button" data-filter=".purple" />
          <div id="brown" class="color-circle button" data-filter=".brown" />
          <div id="black" class="color-circle button" data-filter=".black" />
        </div>
      </div>

      <div class="filter-content show" id="collapse_3">
        <div class="ui-group card-body">
          <input id="price" type="checkbox" />
          <label id="price-label" for="price">
            <i class="down fa fa-caret-down" aria-hidden="true" />Price</label
          >
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
                <label>Min</label>
                <input class="form-control" placeholder="$0" type="number" />
              </div>
              <div class="form-group text-right col-md-6">
                <label>Max</label>
                <input
                  class="form-control"
                  placeholder="$1,0000"
                  type="number"
                />
              </div>
            </div>
            <a href="/" class="button" style="margin-bottom: 30px">Apply</a>
          </div>
          <!-- form-row.// -->
        </div>
        <!-- card-body.// -->
      </div>
    </section>
  </div>
</div>
