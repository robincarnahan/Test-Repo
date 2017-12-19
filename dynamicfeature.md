# To make this website more interesting I decided to add the current date and time.  

That required either writing some javascript (which I don't know) or 💡 better yet, finding some reusable code to do the trick.  After asking *the Google*, I found a handy website called [Moment.js Documentation](https://momentjs.com/docs/#/displaying/) to do just that.

* First step was to decide what information to display such as the day of week, date and time; and

* Adding that javascript in GitHub.

```
<script src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.19.3/moment.min.js"></script>
<script>
document.getElementById("demo").innerHTML = moment().format("dddd, MMMM Do YYYY [at] h:mm a");
</script>
```
