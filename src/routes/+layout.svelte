<script>
  import "../css/index.css";

  let visible = false;
</script>

<header class="center-bellow" id="NavBar">
  <section>
    <div class="cf">
      <a href="/" class="logo">
        <h1><span class="text-primary">LUMINA</span> Shopp</h1>
      </a>
      <div on:click={() => (visible = !visible)} class="E" class:show={visible}>
        <hr />
        <hr />
        <hr />
        <hr />
      </div>
    </div>

    <nav class="c" class:show={visible}>
      <div class="menu">
        <!-- <a class="dropdown" href="/"
          >Decor
          <div>
            <div><a href="/">Mirror</a></div>
            <div><a href="/">Decorative Accessories</a></div>
            <div><a href="/">Window Treatments </a></div>
            <div><a href="/">Throw Pillows</a></div>
          </div>
        </a>
        <a class="dropdown" href="/"
          >Rugs
          <div>
            <div><a href="/">Area Rugs By Size</a></div>
            <div><a href="/">Area Rugs By Color</a></div>
            <div><a href="/">Rugs By Type </a></div>
            <div><a href="/">Trending Rugs</a></div>
          </div>
        </a> -->
        <a class="dropdown" href="/"
          >Categories
          <div>
            <div><a href="/">Applications</a></div>
            <div><a href="/">Lanterns</a></div>
            <div><a href="/">Chandeliers</a></div>
            <div><a href="/">Table Lamps</a></div>
          </div>
        </a>

        <a class="about" href="/">About </a>
        <a class="contact" href="/">Contacts</a>
      </div>

      <div class="header-footer">
        <div class="icon-set-header">
          <a href="/">
            <picture>
              <img src="svg/heart.svg" alt="" />
            </picture>
          </a>
          <a href="/">
            <picture>
              <img src="svg/user.svg" alt="" />
            </picture>
          </a>
          <a href="/">
            <picture>
              <img src="svg/cart.svg" alt="" />
            </picture>
          </a>
        </div>
        <div class="lng">
          <a href="/">BG</a> | <a href="/">EN</a>
        </div>
      </div>
    </nav>
  </section>
</header>

<main>
  <slot />
</main>

<footer>
  <section>
    <div class="p2 c">
      <a href="/" class="logo">
        <h1><span class="text-primary">LUMINA</span> Shopp</h1>
      </a>
      <div class="flex-footer">
        <div>
          <a href="/">Privacy Policy</a>
        </div>
        <div>
          <a href="/">Contact Us</a>
        </div>
      </div>
    </div>
  </section>
  <div class="rights box">
    <section>
      <div>Copyright © 2023 All rights reserved!</div>
      <!-- svelte-ignore a11y-missing-attribute -->
      <div><a href="/" target="_blank"><img src="/svg/user.svg" /></a></div>
    </section>
  </div>
</footer>
