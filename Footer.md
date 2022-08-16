# Footer

Adaption to footer to show impressum.

## Override Footer with theme PaperMod

The theme PaperMod allow to create an extended_footer, sadly the footer is below the original footer.
That is not wh at I want to have, so I decided to disable the original footer and use the extended footer instead.

Disable the standard footer config.yml

```yml
params:
  ...
  hideFooter: true
```

The new extended footer is then place as override in `layouts/partials/extend_footer.html`.
[Custom header or footer](https://github.com/adityatelange/hugo-PaperMod/wiki/FAQs#custom-head--footer)

```html
<footer class="footer">
  <div class="footer_content">      
    {{ range .Site.Menus.footer }}
        <span><a href="{{ .URL | absLangURL }}">{{ .Name }}</a></span>
    {{ end }}
  </div>
  <div>
    {{- if site.Copyright }}
    <span>{{ site.Copyright | markdownify }}</span>
    {{- else }}
    <span>&copy; {{ now.Year }} <a href="{{ "" | absLangURL }}">{{ site.Title }}</a></span>
    {{- end }}
    <span>
        Powered by
        <a href="https://gohugo.io/" rel="noopener noreferrer" target="_blank">Hugo</a> &
        <a href="https://github.com/adityatelange/hugo-PaperMod/" rel="noopener" target="_blank">PaperMod</a>
    </span>
  </div>
</footer>
```

Add custom css to theme PaperMod

To add some costum ccs to PaperMod add the file `assets/css/extended/custom_footer.css`.
[custom css](https://github.com/adityatelange/hugo-PaperMod/wiki/FAQs#bundling-custom-css-with-themes-assets)

```css
.footer_content a {
    color: inherit;
    border-bottom: 0px solid var(--secondary);
}

.footer_content a:hover {
  border-bottom: 1px solid var(--primary);
}
```
