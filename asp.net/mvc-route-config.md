How to way of setting an other Home directory instead of the Default Home directory.

- in the App_Start/RouteConfig.
<pre><code>
  public static void RegisterRoutes(RouteCollection routes)
  {
      routes.IgnoreRoute("{resource}.axd/{*pathInfo}");

      routes.MapRoute(
          name: "Default",
          url: "{controller}/{action}/{id}",
          defaults: new { controller = "Home", action = "Main", id = UrlParameter.Optional }
      );
  }
</code></pre>
