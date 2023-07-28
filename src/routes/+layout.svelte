<script>
  import "../css/index.css";

  let visible = false;
</script>

<header>
  <section>
    <div class="header-flex">
      <div on:click={() => (visible = !visible)} class="E" class:show={visible}>
        <hr />
        <hr />
        <hr />
        <hr />
      </div>
      <div class="logo">
        <a href="/">
          <h1>
            <span class="text-primary">HOME</span> Shopp
          </h1>
        </a>
      </div>

      <nav class:show={visible}>
        <div class="menu">
          <div class="dropdown">
            <a href="/">Decor</a>
            <div>
              <div><a href="/">Mirror</a></div>
              <div><a href="/">Decorative Accessories</a></div>
              <div><a href="/">Window Treatments </a></div>
              <div><a href="/">Throw Pillows</a></div>
            </div>
          </div>
          <div class="dropdown">
            <a href="/">Rugs</a>
            <div>
              <div><a href="/">Area Rugs By Size</a></div>
              <div><a href="/">Area Rugs By Color</a></div>
              <div><a href="/">Rugs By Type </a></div>
              <div><a href="/">Trending Rugs</a></div>
            </div>
          </div>
          <div class="dropdown">
            <a href="/">Lighting</a>
            <div>
              <div><a href="/">Ceiling Lights</a></div>
              <div><a href="/">Wall Lighting</a></div>
              <div><a href="/">Lamps and Lamp Shades</a></div>
              <div><a href="/">Ceiling Fans</a></div>
              <div><a href="/">Outdoor Lighting</a></div>
            </div>
          </div>

          <div class=""><a href="/">About </a></div>
          <div class=""><a href="/">Contacts</a></div>
        </div>

        <div class="icon-set-header">
          <div class="heart">
            <picture>
              <img src="svg/heart.svg" alt="" />
            </picture>
          </div>

          <div class="user">
            <picture>
              <img src="svg/user.svg" alt="" />
            </picture>
          </div>

          <div class="cart">
            <picture>
              <img src="svg/cart.svg" alt="" />
            </picture>
          </div>
        </div>
      </nav>
    </div>
  </section>
</header>

<main>
  <slot />
</main>

<footer>footer</footer>
