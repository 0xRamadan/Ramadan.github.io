# this is the second post


learn how to add an image or figure in a post.

{{< figure src="/images/wallpaper.jpg" title="Programming is fun" alt="a wallpaper conatining some cool code lines" >}}
The images should be put in the 'static' folder.


learing how to highlight:
```python
    # declaring two variables and printing the sum of the two.
    x = 1
    y = 2
    print(x + y)   
    
```
just exploring what gist is:

Gist is one of the many features GitHub provides to its users. GitHub defines2 a Gist as follows: “Gist is a simple way to share snippets and pastes with others. All Gists are Git repositories, so they are automatically versioned, forkable and usable from Git.”

{{< gist spf13 7896402 >}}


just exploring
{{< highlight html >}}
<section id="main">
    <div>
        <h1 id="title">{{ .Title }}</h1>
        {{ range .Pages }}
            {{ .Render "summary"}}
        {{ end }}
    </div>
</section>
{{< /highlight >}}

working wiht showcases:

{{< showcase title="This is My first post" summary="just exploring and discoving more and more about Hugo and its features." image="/images/wallpaperprog.jpg" link="/first_post" >}}






