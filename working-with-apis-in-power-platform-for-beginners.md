# Working with APIs in Power Platform for beginners

Prologue: In this post I'm going to explain what an API is and what it can be used for in Power Automate. I will use the example with a http request for this post, but there will follow others as well. If you want to learn the what and how of APIs, this post is for you.

I recently learned how to work with APIs and the different methods to call them. I started with a straight forward example that's not too complex. I used an open API (that means I don't need authentication for my request) to get the [number of the day](https://math.tools/numbers/number-of-the-day/) from a website called [MathTOOLS](https://math.tools/). I want this number of the day to be posted as a chat message in Microsoft Teams.

Let's start with some theory first

## Whats an API?

API is an acronym for **Application Programming Interface** and they allow applications to communicate with each other and exchange data. An API lists operations that it can perform and which you can use, if you know how to trigger them. Usually the operations are...

- **GET** (read)
- **POST** (write)
- **PUT** (update)
- **PATCH** (update, but only partially)
- **DELETE** (remove)

## How to address APIs?

An API is an interface that you can call and communicate with. You can perform different operations, like getting data, writing things, and so on. But you need to know the correct language, that the API will understand, you need to know the correct direct dial and You need to know what to tell the API to make it do what you want it to do. The language you need is **HTTP**, which is an acronym for **Hypertext Transfer Protocol**.
If the browser on your computer wants to communicate with a server somewhere on the world, it sends an **HTTP request** (it asks politely) and when we did everything in the right way, we will get a polite answer, an **HTTP response**.

An **HTTP request** gives us the ability to communicate with an **API**. So much for the theory, now let's get our hands dirty 👏 and let's see how it looks in Power Automate.

## HTTP request

As I mentioned earlier an **HTTP request** consists of a view things. We will need a...

- Method
- URL
- Headers
- and a body

![a picture showing the HTTP action in Power Automate](https://GitHub.com/MichaelRoth42/Juicy-Blog-Stuff/blob/main/media/HTTPrequest.png)

### Method

Luckily we know the methods already.

| METHOD | ACTION |
| --- | --- |
| GET | read |
| PUT | update |
| POST | write |
| PATCH | update partially |
| DELETE | remove |

In this usecase we want to **get** the number of the day, so we choose the **GET** method.

## URL

Now for the URL we need to know the **URL** (kind of obvious, isn't it 😁) of the service we want to address. But not only that, we will also need the **endpoint**. This is something like the direct call, putting you to that exact point that you want. Usually an API will tell you how the endpoint looks: 

![a picture showing the api from the math tool site](https://GitHub.com/MichaelRoth42/Juicy-Blog-Stuff/blob/main/media/api-math-tool.png)

The endpoint of the website MathTOOLS is `https://api.math.tools`, but if we read carefully (I usually struggle with that 😇), we get more details for the API of the number of the day:

![a picture showing api from the number of the day](https://GitHub.com/MichaelRoth42/Juicy-Blog-Stuff/blob/main/media/api-math-tool.png)

The endpoint for the number of the day is `https://api.math.tools/numbers/nod`. The API documentation even provides us with the information of how the HTTP response will look like:

![a picture showing the response from calling the api from the number of the day](https://GitHub.com/MichaelRoth42/Juicy-Blog-Stuff/blob/main/media/JSON-nod.png)

It's a very long JSON object (if you want to get started with JSON, I recommend the amazing blog from Bob German [Introduction to JSON](https://bob1german.com/2021/01/11/introduction-to-json/)).
But let's stay at our HTTP request in Power Automate. We know the Method, we know the URL and we know that we don't need any authentication. That means we can fill out all mandatory fields in that flow action and it looks like this:

![a picture showing the filled out http request in flow](https://GitHub.com/MichaelRoth42/Juicy-Blog-Stuff/blob/main/media/http-flow-step.png)

Let's run this flow on a daily basis and see what the result looks like:

![a picture showing the result of the flow](https://GitHub.com/MichaelRoth42/Juicy-Blog-Stuff/blob/main/media/http-flow-run-successfull.png)

(Since you can hardly see the result, I paste the body here once again)

![a picture showing the result of the flow again, but different](https://GitHub.com/MichaelRoth42/Juicy-Blog-Stuff/blob/main/media/http-flow-result.png)

And that's it, we used an **HTTP request** to **GET** information from a **API**. Now for the last part of this blog, we want to use some information from this result to be posted in a chat in Teams.

## Use a certain information from a JSON object in a chat message



Next up: What's a custom connector, difference between http request and custom connector, when to use what and how to build one