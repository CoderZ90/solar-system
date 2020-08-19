# solar-system using html and css

# CDN links

     <script src="https://cdnjs.cloudflare.com/ajax/libs/prefixfree/1.0.7/prefixfree.min.js"></script>

# JQuery links

    <script src="//ajax.googleapis.com/ajax/libs/jquery/1.8.1/jquery.min.js"></script>
        <script type="text/javascript">
        if (typeof jQuery == 'undefined') { 
          document.write(unescape("%3Cscript src='js/jquery.min.js' type='text/javascript'%3E%3C/script%3E"));
        }
        </script>
        <script src="js/prefixfree.min.js"></script>
        <script src="js/scripts.min.js"></script>

        <!-- partial -->
      <script src='https://cdnjs.cloudflare.com/ajax/libs/jquery/2.1.3/jquery.min.js'></script><script  src="./script.js"></script>
      
# JS file code

      $(window).load(function(){

        var body = $("body"),
            universe = $("#universe"),
            solarsys = $("#solar-system");

        var init = function() {
          body.removeClass('view-2D opening').addClass("view-3D").delay(2000).queue(function() {
            $(this).removeClass('hide-UI').addClass("set-speed");
            $(this).dequeue();
          });
        };

        var setView = function(view) { universe.removeClass().addClass(view); };

        $("#toggle-data").click(function(e) {
          body.toggleClass("data-open data-close");
          e.preventDefault();
        });

        $("#toggle-controls").click(function(e) {
          body.toggleClass("controls-open controls-close");
          e.preventDefault();
        });

        $("#data a").click(function(e) {
          var ref = $(this).attr("class");
          solarsys.removeClass().addClass(ref);
          $(this).parent().find('a').removeClass('active');
          $(this).addClass('active');
          e.preventDefault();
        });

        $(".set-view").click(function() { body.toggleClass("view-3D view-2D"); });
        $(".set-zoom").click(function() { body.toggleClass("zoom-large zoom-close"); });
        $(".set-speed").click(function() { setView("scale-stretched set-speed"); });
        $(".set-size").click(function() { setView("scale-s set-size"); });
        $(".set-distance").click(function() { setView("scale-d set-distance"); });

        init();

      });
