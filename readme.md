# Test hugo website

I am currently migrating an old set of websites to Hugo. Those websites are marketing websites and have some specific SEO tags to set in the header.

There are a lot of awesome themes available for Hugo but they are all implemented there way.

What I would like to achieve is :

- Migrate my old websites ( 1000+ ) to hugo
- Be able to use a random theme for each site
- Add/Override tags in the ```<head>``` of each theme to set my custom info (ex: SEO info) :
  - Title
  - Meta
  - Opengragh
  - Anything I can generate fromt the front mattter


I have installed 3 themes and they all have different approaches to deal with the ```<head>```

- ananke -> ```<head>``` define directly in a baseof.html
- arabica -> ```<head>``` define in partial head.html
- liva-hugo -> ```<head>``` define in partial head.html + using assets like scss

I can **easily** override each theme but if I want to do it at a bigger scale : as themes do not follow the same patterns, I do not know how to proceed.

I have tried to use **Theme components** to override parts. I have tried to narrow down the number of themes to find the ones that are built the same way.

#### But I was wondering if we could think at a more generic approach :
- For each generated content we generate a specific partial based on the current content data (front matter) and then
- Replace some parts of the generated content with the partial generated

I was thinking to use **Custom Output Formats** to generate what I want, but then I would need to somehow hook in the generation process to manipulate the output.

Maybe the easiest is to manage this part outside of Hugo itself in a dedicated build pipeline but I was just wondering if this is doable with the current Hugo features ?