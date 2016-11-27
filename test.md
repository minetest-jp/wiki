---
layout: default
---
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.1.1/jquery.js"></script>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/ResponsiveSlides.js/1.53/responsiveslides.min.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/ResponsiveSlides.js/1.53/responsiveslides.min.js"></script>
<script>
  $(function() {
    $(".slide").responsiveSlides({
      auto    : true,
      pause   : true,
      speed   : 500,
      timeout : 4000
    });
  });
</script>

<div align="center">
  <ul class="slide" style="width: 350px; height: 250px; box-shadow: 0 10px 10px -10px #777">
    <li><img src="http://minetest.wiki.fc2.com/image/screenshot_1.png"></li>
    <li><img src="http://minetest.wiki.fc2.com/image/screenshot_2.png"></li>
  </ul>
</div>
