## Using bash scripts

As a java developer I am not writing small scripts and programs on a daily basis. 

However, sooner or later the need arises to solve some small task. In the organization I am working in we have a duty of solving ongoing problems, called "bug runner". Usually a person acts as a runner half of the sprint, in our case that would be one week. During the shift the runner gets all the problems regular users struggle with and solves them.

Often it mean that some process in our organization went wrong, and manual action is required. For example, runner needs to add or remove something from the database or make a rest call to some endpoint.

The tasks and tools vary, and this leads to a lot of manual input an then to mistakes.

For example, the REST endpoint needs to be called. This could be easily done via program such as `curl`, but imagine that you need to do two or three calls, and answers is json-formatted, and the output of one call partly becomes the parameters of another. It is very easy to make a mistake in this process.
//example of the curl call from Theo

So let's wrap it in the bash script!

The starting script could be very simple:

```
#!/bin/bash
`curl https://... -H="X_MY_HEADER: header value"`
```

Notice, all we did is just stored the curl call in the script, so at least next time we could reuse it changing the file a bit.

But what if we want to use the script several times in a row? It's better to get the parameters out of the script itself.

```
Example with parameters out. 
```

Better, now I can not only run it manually with different parameters, but also automate it and use it from different programs!

Now, what if the parameters provided are wrong? For example, organisation I'd can be only integer. Or user has entered only three parameters? We shall check the input!

```
Checking the input
```