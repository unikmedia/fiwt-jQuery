#Fill It With Tweets

**FIWT** - Plugins to easily get a twitter feed on your website

***

##Dependencies (all in the repository)

jQuery, handlebars.js, [timeago](http://timeago.yarp.com/)

##Set a twitter api account

*All these settings are in the hook.php*

Go to [https://dev.twitter.com/apps](https://dev.twitter.com/apps) and create a new application.

You must provide for this plugin the **OAuth settings**, *Consumer key* and *Consumer secret*, from the new application.

You have to create <strong>your access token</strong> in the bottom of the page and write the <em>access token</em> and the <em>access token secret</em> in the script.


##Usage

jQuery usage

    $('#tweets').fillItWithTweets({
        template: '#twTemplate',
        username: 'unik_media', 
        container: '#tweets',
    });
    
All attributes

`template`: *(css selector (string))* the script id for the handlebars template,
`username`: *(string)* the twitter username without `@`, 
`container`: *(css selector (string))* same string as the selector,
`count`: *(int)* the number of tweet to show,
`debug`: *(bool)* to get the result in the console,
`eachAppended`: *(bool)* to append the `{{#each tweets}}`,
`messageLoading`: *(string)* loading message,
`beforeRender`: *(function)* Callback before the render,
`afterRender`: *(function)* Callback after the render,

##Create the tweet template

The tweet template works with [handlebars.js](http://handlebarsjs.com/)

You must create only an `<li>` template and it will repeat for each tweet.

There's an exemple
    
    <script id="twTemplate" type="text/x-handlebars-template">
    {{#each tweets}}
        <li>
            <a href="https://twitter.com/{{user.screen_name}}">
                <img alt="{{user.screen_name}}" src="{{user.profile_image_url}}" />
            </a>
            <article>{{tweet text}}</article>
        </li>
    {{/each}}
    </script>
    
The data in the template is the tweet object returned. If you want to check the whole object [this pastebin](http://pastebin.com/FgLU1N66)
