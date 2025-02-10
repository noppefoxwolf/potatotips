

Hello, My name is Tomoya Hirano.
Today is my first time giving a presentation in English.
I'm an iOS app developer at DeNA in Tokyo.

---

Today I want to talk about import, which is a function of Swift.
I think many of us use import without really thinking about it.
But did you know that there are a few options?

---

In fact, there are three syntaxes for import.
These syntaxes can be found in swift documents.
Some tokens add to the import syntax we usually use.
Let's look at each token.

---

First, I will introduce attributes.

---

Attributes are an option for specifying how to import symbols.
You don't have to write this.
Today there are two symbols in Swift, @testable and @_exported.

---

Testable is an attribute to use for testing.
If you write it before the import, you can access internal methods.

---

@_exported is used to import symbols as though they were your own code.
The underscore stands for private.
But it is not recommended, and you should use it in the development phase only.

---

Next, let's look at how to specify a submodule.
When a submodule is specified, if becomes possible to import the submodule implementation.

---

There is a good example of submodule usage in SceneKit.
SceneKit has extensions that allow it to create scenes from the ModelIO class, and make models from scenes.

---

So SceneKit declares the ModelIO as a submodule.
You can see that by designating and implementing the submodule, the number of contractors in SCNScene increases.

---

Lastly, I will introduce the third syntax.
If you specify the kind, it will import the specified element.
For example, if you want to only import the User class, you would write "User" after the module name.

---

kind can specify struct, class,  enum, protocol, typealias, func, let and var.
These are the same elements as you see in Swift.

---

But, please note two things.
Firstly, about import class or struct.
swift will import all accessible methods and properties in class or struct.
You can import methods and properties using `kind` limiting what is implemented in the top-level.
Secondly, about overloaded functions.
You cannot import them separately. 

---

Now, I introduced some import options using kinds.
When you are declaring different modules using functions of the same name, you will need to use the following notation.
For example, the Cat module and Fox module have the printEmoji function.
The printEmoji outputs the module name animal.

---

If you import both these modules, you will get an error.
Imports using kind prioritize finding methods.

---

Now I've covered the import options.
Using them can be challenging, but let's look at some clear benefits.

---

Let's measure the build time.  

---

I made 100,000(a hundred thousand) methods.
and then compared the build time when declaring the kind and not declaring it.

---

The result is that it was almost the same.
So, how about the binary size?

---

This was also the same.
And the md5 of the binary files was the same too.
What this means, is that no matter your notation, the Swift compiler optimizes so that the result is the same.

---

These are the Pros and Cons.
According to this table, there is no need to write import in detail, unless there are any problems with the namespace.
You should write your code the same as you always have.
Thank you for listening. 