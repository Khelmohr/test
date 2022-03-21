## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/Khelmohr/test/edit/main/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

  
  
  <!-- Load iFrameXJS -->
  <script src="../iFrameX/dist/iframex.min.js"></script>
  
  <!-- Example button -->
  <script onload="createIframe()"></script>
  
  <!--- Create variable and functions for initialize iFrameX with configuration -->
    <script>
    let iframe = null;
    const table = `<thead> <tr> <th scope="col">#</th> <th scope="col">First</th> <th scope="col">Last</th> <th scope="col">Handle</th> </tr></thead> <tbody> <tr> <th scope="row">1</th> <td>Mark</td><td>Otto</td><td>@mdo</td></tr><tr> <th scope="row">2</th> <td>Jacob</td><td>Thornton</td><td>@fat</td></tr><tr> <th scope="row">3</th> <td>Larry</td><td>the Bird</td><td>@twitter</td></tr></tbody>`;
    const options = {
      attributes: {
        width: '100%',
        height: '600',
        class: 'nice-iframe',
      },
      content: [
        {
          type: 'link',
          append: 'head',
          attr: {
            href: 'https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css',
            rel: 'stylesheet',
          },
        },
        {
          type: 'div',
          content: 'A simple primary alert—check it out!',
          attr: {
            class: 'alert alert-primary',
            role: 'alert',
          },
        },
        {
          type: 'table',
          content: table,
          attr: {
            class: 'table',
          },
        },
        {
          type: 'h1',
          append: 'div.alert',
          content: 'Hi',
          attr: {
            class: 'mydiv',
          },
        },
        {
          type: 'script',
          content: 'window.document.addEventListener("CustomEventName", event => console.log(event.detail))', // Iframe listener
          attr: {
            async: true,
          },
        },
        {
          type: 'script',
          content: 'window.parent.document.dispatchEvent(new CustomEvent("CustomEventName", { detail: {date: new Date(), message: "Sent from iframe to parent."} }))', // Iframe sender
          attr: {
            async: true,
          },
        },
      ],
      options: {eventName: 'CustomEventName'}
    };

    async function createIframe(){
      iframe = new iFrameX(options);
      iframe.create();
      iframe.gateway = function (data) { // Parent listener
        console.log(data);
        iframe.sendMessage('CustomEventName', {date: new Date(), message: "Sent from parent to iframe"}); // Parent sender
      }
    }
  </script>



### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/Khelmohr/test/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.

<script>
  
async function createIframe(){
      iframe = new iFrameX(options);
      iframe.create();
      iframe.gateway = function (data) { // Parent listener
        console.log(data);
        iframe.sendMessage('CustomEventName', {date: new Date(), message: "Sent from parent to iframe"}); // Parent sender
      }
    }

</script>
