Run

`npx tailwindcss -o tailwind.css`


to see that the generated CSS file contains:

```css

.text-sm {
  font-size: 0.875rem;
  line-height: 1.25rem;
}

.text-yellow-50 {
  --tw-text-opacity: 1;
  color: rgba(255, 251, 235, var(--tw-text-opacity));
}

.text-yellow-100 {
  --tw-text-opacity: 1;
  color: rgba(254, 243, 199, var(--tw-text-opacity));
}
```
and nothing about `.text-lg`

The view file contains:

```haml
%h1 Articles#index
- name = "Find me in app/views/articles/index.html.erb"
%p.text-yellow-50.text-lg=name
%p.text-yellow-100.text-sm
  = name
 ```
 
The `text-lg` is not parsed by tailwind, probably due to the following `=name` which is a valid syntax in haml.
