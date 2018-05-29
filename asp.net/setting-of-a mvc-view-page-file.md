## An issue of a Html.RenderPartial File Path
- Here is a View page, 'Html.RenderPartial("\~/Areas/Reviews/Views/Post", Model)'
- The renderer did not find other 'Areas' view page, but even the page exists clearly.
- So, I added the file extension string on the path, it solved. :)

```c#
Html.RenderPartial("\~/Areas/Reviews/Views/Post", Model)
 VS
Html.RenderPartial("\~/Areas/Reviews/Views/Post.cshtml", Model)
```
