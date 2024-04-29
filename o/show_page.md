# Show me the page
`Apr 29, 2024`

Today I made some changes to this website. 

Originally I use a pair of `.htm` and `.md` files to parse the markdown file and show the page.

For example, `the_page.htm` and `the_page.md`.

But now, I only use a single html page to parse all the markdown files.

The page url will be like: `s.htm?p=the_page`

It means, **s**how me the **p**age :-D
- `s.htm` means <u>s(how)</u>.htm
- `p=the_page` means the <u>p(age)</u> is `the_page`

The code with comments is here:

<main>
  <script>
  document.addEventListener('DOMContentLoaded', function() {
  const searchParams = new URLSearchParams(window.location.search);
  var md_file = searchParams.get('p') + ".md";
  
  // Select the <zero-md> element
  var zeroMdElement = document.querySelector('zero-md');
  
  // Check if the element exists before setting the src attribute
  if (zeroMdElement) {
  
  // Set the src attribute with the value of md_file variable
  zeroMdElement.setAttribute('src', md_file);
  } else {
  console.error('Zero-MD element not found');
  }
  });
  </script>
<zero-md></zero-md>
</main>

Actually I knew almost nothing about JavaScript, so I asked ChatGPT and learned how to do this, by chatting with AI, it's helpful, thanks.
