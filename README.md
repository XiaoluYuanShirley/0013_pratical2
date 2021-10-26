# 0013_pratical2
{
 "cells": [
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "<div style=\"float:left\">\n",
    "    <h1 style=\"width:450px\">Practical 3: Foundations (Part 2)</h1>\n",
    "    <h2 style=\"width:450px\">Getting to grips with Dictionaries, LOLs and DOLs</h2>\n",
    "</div>\n",
    "<div style=\"float:right\"><img width=\"100\" src=\"https://github.com/jreades/i2p/raw/master/img/casa_logo.jpg\" /></div>"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Here's a short introduction to Practical 3.\n",
    "\n",
    "[![Practical 3 Video](https://github.com/jreades/i2p/raw/master/practicals/img/Practical_3_Still.png)](https://web.microsoftstream.com/video/217679a2-dd13-4552-b299-339d82ff7c1a)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "<div style=\"border: dotted 1px rgb(156,121,26); padding: 10px; margin: 5px; background-color: rgb(255,236,184); color: rgb(156,121,26)\"><i>Note</i>: You should download this notebook from GitHub and then save it to your own copy of the repository. I'd suggest adding it (<tt>git add ...</tt>) right away and then committing (<tt>git commit -m \"Some message\"</tt>). Do this again at the end of the class and you'll have a record of everything you did, then you can <tt>git push</tt> it to GitHub.</div>"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## Task 1. From Lists to Data (Little Steps)\n",
    "\n",
    "We're going to start off using lists and dictionaries that _we_ define right at the start of the 'program', but the _real_ value of these data structures comes when we build a list or dictionary _from_ data such as a file or a web page... and that's what we're going to do below!"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "First, here's a reminder of some useful methods (_i.e._ functions) that apply to lists:\n",
    "\n",
    "| Method                 | Action |\n",
    "|------------------------|------------------------------------------------------------------|\n",
    "| list.count(`x`)        | Return the number of times x appears in the list                 |\n",
    "| list.insert(`i`, `x`)  | Insert value `x` at a given position `i`                         |\n",
    "| list.pop([`i`])        | Remove and return the value at position `i` (`i` is optional)    |\n",
    "| list.remove(`x`)       | Remove the first element from the list whose value is `x`        |\n",
    "| list.reverse()         | Reverse the elements of the list in place                        |\n",
    "| list.sort()            | Sort the items of the list in place                              |\n",
    "| list.index(`x`)        | Find the first occurence of `x` in the list                      |\n",
    "| list[x:y]              | Slice the list from index `x` to `y-1`                           |\n",
    "\n",
    "This should all be revision... because it's how we finished things up _last week_. But I want to go over it _briefly_ again because we're going to build on it this week.\n",
    "\n",
    "<div style=\"border: dotted 1px green; padding: 10px; margin: 5px; background-color: rgb(249,255,249);\"><i>Hint</i>: As before, `??` will highlight where one or more bit of code are missing and need to be filled in...</div>"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Task 1.1 List Refresher\n",
    "\n",
    "Replace `??` in the following code blocks to make the code work as instructed. All of the methods that you need are listed above, so this is about testing yourself on your understanding *both* of how to read the help *and* how to index elements in a list."
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "The next line creates a list of city names (each element is a string):"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "cities = [\"Bristol\", \"London\", \"Manchester\", \"Edinburgh\", \"Belfast\", \"York\"]"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "**a)** Replace the `??` so that it prints the _index_ for Manchester in the list"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "print(\"The position of Manchester in the list is: \" + str( ?? ))"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "**b)** Replace the `??` so that it prints Belfast"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "print(cities[?? + 2])"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "**c)** Use a **negative** index to print *Belfast*"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "print(cities[??])"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Task 1.2 Looking Across Lists"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Notice that the list of `temperatures` below is the same length as the list of `cities`, that's because these are (roughly) average temperatures for each city!"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "temperatures = [15.6, 16.5, 13.4, 14.0, 15.2, 14.8]"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "**a)** Given what you know about `cities` and `temperatures`, how do you print: \n",
    "\n",
    "> \"The average temperature in Manchester is 13.4 degrees.\"\n",
    "\n",
    "_without_ doing any of the following:\n",
    "1. Using a list index directly (*i.e.* `cities[2]` and `temperatures[2]`) or \n",
    "2. Hard-coding the name of the city? \n",
    "\n",
    "To put it another way, **neither** of these solutions is the answer:\n",
    "```python\n",
    "print(\"The average temperature in Manchester is \" + str(temperatures[2]) + \" degrees.\")\n",
    "```\n",
    "or \n",
    "```python\n",
    "city=2\n",
    "print(\"The average temperature in \" + cities[city] + \" is \" + str(temperatures[city]) + \" degrees.\")\n",
    "```\n",
    "\n",
    "<div style=\"border: dotted 1px green; padding: 10px; margin: 5px; background-color: rgb(249,255,249);\"><i>Hint</i>: You will need to combine some of the ideas above and also think about the fact that the list index is that we need is the same in both lists... Also, remember that you'll need to wrap a `str(...)` around your temperature to make it into a string.</div>"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "city=\"Manchester\" # Use this to get the solution...\n",
    "print(\"The average temperature in \" + city + \" is \" + ??)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "You'll know that you got the 'right' answer to the question above if you can copy+paste your code and change only **one** thing in order to print out: \"The average temperature in Belfast is 15.2 degrees\""
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "city=\"Belfast\"\n",
    "?? # You code from the previous cell"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "**b)** Can you convert this to a simple function called `avg_tmp` with two inputs and then use this to print the average temperature for Edinburgh? "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "def ??(??, ??):\n",
    "    print(f\"The average temperature in {??} is {??}\")\n",
    "\n",
    "city=\"Edinburgh\"\n",
    "avg_tmp(city, ??)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "The output should be: `The average temperature in Edinburgh is 14.0`"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "**c)** Now use a `for` loop over the cities to print out the average temperature in each city using the function that we just created:"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "for c in cities:\n",
    "    avg_tmp(??, ??)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "The output should be:\n",
    "```\n",
    "The average temperature in Bristol is 15.6\n",
    "The average temperature in London is 16.5\n",
    "The average temperature in Manchester is 13.4\n",
    "The average temperature in Edinburgh is 14.0\n",
    "The average temperature in Belfast is 15.2\n",
    "The average temperature in York is 14.8\n",
    "```"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## Task 2. Dictionaries\n",
    "\n",
    "Remember that dictionaries (a.k.a. dicts) are like lists in that they are [data structures](https://docs.python.org/2/tutorial/datastructures.html) containing multiple elements. A key difference between [dictionaries](https://docs.python.org/2/tutorial/datastructures.html#dictionaries) and [lists](https://docs.python.org/2/tutorial/introduction.html#lists) is that while elements in lists are ordered, dicts are unordered. This means that whereas for lists we use integers as indexes to access elements, in dictonaries we use 'keys' (which can multiple different types; strings, integers, etc.). Consequently, an important concept for dicts is that of key-value pairs. "
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Task 2.1 Creating an Atlas"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "The code below creates an Atlas using a dictionary. The dictionary `key` is a city name, and the `value` is the latitude, longitude, and main airport code."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "cities = {\n",
    "    'San Francisco': [37.77, -122.43, 'SFO'],\n",
    "    'London': [51.51, -0.08, 'LDN'],\n",
    "    'Paris': [48.86,2.29, 'PAR'],\n",
    "    'Beijing': [39.92,116.40 ,'BEI'],\n",
    "}"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "**a)** Add a record to the dictionary for Chennai ([data here](https://en.wikipedia.org/wiki/Chennai))"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "**b)** In *one* line of code, print out the airport code for Chennai (`MAA`):"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Task 2.2 Dealing With Errors\n",
    "**a)** Check you understand the difference between the following two blocks of code by running them."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "print(cities['Berlin'])"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "print(cities.get('Berlin'))"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Task 2.3 Thinking Data\n",
    "\n",
    "<div style=\"border: dotted 1px green; padding: 10px; margin: 5px; background-color: rgb(249,255,249);\"><i>Hint</i>: In this section you'll need to look up (i.e. Google) and make use of a few new functions that apply to dictionaries: <tt>&lt;dictionary&gt;.items()</tt>, <tt>&lt;dictionary&gt;.keys()</tt>. <i>Remember</i>: if in doubt, add <tt>print(...)</tt> statements to see what is going on!</div>\n",
    "\n",
    "**a)** Adapting the code below, print out the city name and airport code for every city in our Atlas."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "for k, v in cities.items():\n",
    "    ??"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "The output should look something like this:\n",
    "```\n",
    "San Francisco -> SFO\n",
    "London -> LDN\n",
    "Paris -> PAR\n",
    "Beijing -> BEI\n",
    "Chennai -> MAA\n",
    "```"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "**b)** How would your code need to change to produce the _same output_ from this data structure:"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "cities = {\n",
    "    'San Francisco': {\n",
    "        'lat': 37.77, \n",
    "        'lon': -122.43,\n",
    "        'airport': 'SFO'},\n",
    "    'London': {\n",
    "        'lat': 51.51, \n",
    "        'lon': -0.08, \n",
    "        'airport': 'LDN'},\n",
    "    'Paris': {\n",
    "        'lat': 48.86,\n",
    "        'lon': 2.29, \n",
    "        'airport': 'PAR'},\n",
    "    'Beijing': {\n",
    "        'lat': 39.92,\n",
    "        'lon': 116.40,\n",
    "        'airport': 'BEI'},\n",
    "    'Chennai': { \n",
    "        'lat': 13.08, \n",
    "        'lon': 80.28, \n",
    "        'airport': 'MAA'}\n",
    "}\n",
    "\n",
    "for k, v in cities.items():\n",
    "    ??"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "**c)** And how would it need to change to print out the name and latitude of every city?"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "for c in cities.keys():\n",
    "    ??"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "The output should be something like this:\n",
    "```\n",
    "San Francisco is at latitude 37.77\n",
    "London is at latitude 51.51\n",
    "Paris is at latitude 48.86\n",
    "Beijing is at latitude 39.92\n",
    "Chennai is at latitude 13.08\n",
    "```"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "**d)** Now produce the _same output_ using this new data structure:"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "cities_alt = [\n",
    "    {'name':     'San Francisco',\n",
    "     'position': [37.77, -122.43],\n",
    "     'airport':  'SFO'},\n",
    "    {'name':     'London',\n",
    "     'position': [51.51, -0.08],\n",
    "     'airport':  'LDN'},\n",
    "    {'name':     'Paris',\n",
    "     'position': [48.86, 2.29],\n",
    "     'airport':  'PAR'},\n",
    "    {'name':     'Beijing',\n",
    "     'position': [39.92, 116.40],\n",
    "     'airport':  'BEI'},\n",
    "    {'name':     'Chennai', \n",
    "     'position': [13.08, 80.28],\n",
    "      'airport': 'MAA'}\n",
    "]\n",
    "\n",
    "for c in cities_alt:\n",
    "    ??"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "**e)** What are some of the main differences that you can think of between `cities` and `cities_alt` _as_ data? There is no right answer.\n",
    "\n",
    "<div style=\"border: dotted 1px green; padding: 10px; margin: 5px; background-color: rgb(249,255,249);\"><i>Hint</i>: I just want you to think about these <i>as data</i>! If you were trying to use <tt>cities</tt> and <tt>cities_alt</tt> as data what differences would you find when accessing one or more 'records'?</div>\n",
    "\n",
    "- Point 1\n",
    "- Point 2\n",
    "- Point 3"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## Task 3. Tackling Programming Problems\n",
    "\n",
    "Let's now think about how to approach problems in programming (with code) and how that might differ from other ways of thinking. \n",
    "\n",
    "The problem we will use here as an example is: _download a data file that we know is hosted on a web site and output some information about those data_. This sounds hard. It _is_ hard when you're just starting out in programming. But it is _not_ hard for a computer... _iff_ we can figure out what to tell it to do _and_ make use of work that other people have done for us!"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "### What Do We Do? Break It Down!\n",
    "\n",
    "![Break it down cartoon](https://img.memecdn.com/break-it-down_o_1384575.gif)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "##### Step 1. Analyse the Problem\n",
    "\n",
    "The first step to writing a program is thinking about your goal and the steps required to achieve that. We _**don't**_ write programs like we write essays: all at once by writing a whole lot of code and then hoping for the best when we hit 'submit'. \n",
    "\n",
    "When you're tackling a programming problem you break it down into separate, simpler steps, and then tick them off one by one. Doing this gets easier as you become more familiar with programming, but it remains crucial and, in many cases, good programmers in large companies spend more time on _design_ than they do on actual _coding_."
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "##### Step 2. Functions & Packages\n",
    "\n",
    "We have discussed how _functions_ are a useful programming tool to enable us to re-use chunks of code. Basically, a function is a way to do something to something in a portable, easy-to-use little bundle of code. "
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Some steps in a program are done so many times by so many people that, eventually, someone writes a _package_ that bundles up those operations into something easy to use that saves _you_ having to figure out the gory details. Reading a file (even one on a computer halfway round the world) is one of those things. Analysing a data file for you is probably not.\n",
    "\n",
    "![xkcd: Easy vs. Hard](https://imgs.xkcd.com/comics/tasks.png)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "To a computer, reading data from a remote location (e.g. a web site halfway around the world) is not really any different from reading one that's sitting on your your local hard drive (e.g. on your desktop). To simplify things a great deal: the computer really just needs to know the location of the file and an appropriate _protocol_ for accessing that file (_e.g._ http, https, ftp, local...) and then a clever programming language like Python will typically have packages that can take care of the rest. \n",
    "\n",
    "In all cases -- local and remote -- you use the package to handle the hard bit of knowing how to actually 'read' data (because all files are just `1`s and `0`s of data) at the _device_ level and then Python gives you back a 'file handle' that helps you to achieve things like 'read a line' or 'close an open file'. You can think of a filehandle as something that gives you a 'grip' on a file-like object no matter where or what it is, and the package is the way that this magic is achieved."
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "##### Step 3. Look for Ways to Recycle"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "**Always** look for ways to avoid reinventing the wheel. This is where Python's packages (or R's for that matter) come into their own. If it's something that programmers often need to do, then chances are that someone has written a package to do it!\n",
    "\n",
    "The point of packages is that they can help us to achieve quite a lot very quickly since we can just make use of someone else's code. In the same way that we won't mark you down for Googling the answer to a coding question, we _also_ won't mark you down for using someone else's package to help you get going with your programming. _**That's the whole point!**_\n",
    "\n",
    "Often, if you're not sure where to start, Google (or StackOverflow) is the place to go:\n",
    "\n",
    "[`how to read text file on web server python`](https://www.google.co.uk/search?q=how+to+read+text+file+on+web+server+python&oq=how+to+read+text+file+on+web+server+python&aqs=chrome..69i57.629j0j7&sourceid=chrome&ie=UTF-8)\n",
    "\n",
    "Boom!"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "##### Step 4. Make a Plan\n",
    "\n",
    "OK, so we need to break this _hard_ problem down into something simpler. We can do this by thinking about it as three separate steps:\n",
    "\n",
    "1. We want to read a remote file (i.e. a text file somewhere the planet), \n",
    "2. We want to turn it into a local data structure (i.e a list or a dictionary), \n",
    "3. We want to perform some calculations on the data (e.g. calculate the mean, find the easternmost city, etc.).\n",
    "\n",
    "We can tackle each of those in turn, getting the first bit working, then adding the second bit, etc. It's just like using lego to build something: you take the same pieces and assemble them in different ways to produce different things."
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Task 3.1. Reading a Remote File\n",
    "\n",
    "So, we are going to download a file from GitHub: [https://github.com/jreades/i2p/raw/master/data/2020-08-24-sample-listings-simple.csv](https://github.com/jreades/i2p/raw/master/data/2020-08-24-sample-listings-simple.csv).\n",
    "\n",
    "We aren't going to to try to turn it into data or otherwise make 'sense' of it yet, we just want to **read** it. We are then going to build from this first step towards the rest of the steps!\n",
    "\n",
    "Because we're accessing data from a 'URL' we need to use the `urlopen` [function](https://docs.python.org/3.0/library/urllib.request.html?highlight=urlopen#urllib.request.urlopen) from the `urllib.request` [package](https://docs.python.org/3.0/library/urllib.request.html). \n",
    "\n",
    "If you're wondering how we know to use this function and package, you might google something like: _read remote csv file python 3_ which in turn might get you to a StackOverflow question and answer like [this](https://stackoverflow.com/questions/36965864/opening-a-url-with-urllib-in-python-3). \n",
    "\n",
    "<div style=\"border: dotted 1px green; padding: 10px; margin: 5px; background-color: rgb(249,255,249);\"><i>Hint</i>: Remember that you can use <tt>dir(...)</tt> and <tt>help(...)</tt> to investigate what a package offers.</div>"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "<div style=\"border: dotted 1px rgb(156,121,26); padding: 10px; margin: 5px; background-color: rgb(255,236,184); color: rgb(156,121,26)\"><i>Note</i>: You can also get help in Jupyter by typing <tt>?</tt> before the function that you want to call.</div>"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "from urllib.request import urlopen\n",
    "?urlopen"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "As you can see, there is _lot_ of information here about how things work. A _lot_ of it won't make much sense at the moment. That's ok. _Some_ of this doesn't make much sense to me, but that's because this is the _full_ documentation from Python so it's trying to cover _all_ the bases. You don't need to read every line of this, what you are looking is information about things like the 'signature' (what parameters the function accepts) and its output. Of course, you can also _just Google it_!"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "<div style=\"border: dotted 1px rgb(156,121,26); padding: 10px; margin: 5px; background-color: rgb(255,236,184);\"><i>Note</i>: if you are in China or working behind a firewall then there is a <i>chance</i> you will get a <tt>URLError</tt> (<tt>&lt;urlopen error [Errno 110044] getaddrinfo failed&gt;</tt>). This is a '<a href=\"https://stackoverflow.com/questions/7334199/getaddrinfo-failed-what-does-that-mean\">proxy error</a>' and in this case you may need to <a href=\"https://stackoverflow.com/a/28153935\">configure your environment</a> as follows:<br />\n",
    "<tt>\n",
    "import os<br />\n",
    "os.environ['HTTP_PROXY'] = 'http://127.0.0.1:10809'<br />\n",
    "os.environ['HTTPS_PROXY'] = 'http://127.0.0.1:10809'<br />\n",
    "</tt>\n",
    "</div>"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "from urllib.request import urlopen\n",
    "\n",
    "# Given the info you were given above, what do you \n",
    "# think the value of 'url' should be? What\n",
    "# type of variable is it? int or string? \n",
    "url = 'https://github.com/jreades/i2p/raw/master/data/2020-08-24-sample-listings-simple.csv'\n",
    "\n",
    "# Read the URL stream into variable called 'response'\n",
    "# using the function that we imported above\n",
    "response = urlopen(url)\n",
    "\n",
    "# Now read from the stream, decoding so that we get actual text\n",
    "datafile = response.read().decode('utf-8')\n",
    "\n",
    "# You might want to explore what `__class__` and `__name__`\n",
    "# offer, but basically the give us a way of finding out what\n",
    "# is 'behind' more complex variables\n",
    "print(\"datafile variable is of type: '\" + datafile.__class__.__name__ + \"'.\\n\")"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "<div style=\"border: dotted 1px rgb(156,121,26); padding: 10px; margin: 5px; background-color: rgb(255,236,184); color: rgb(156,121,26)\"><i>Note</i>: The <tt>datafile</tt> variable is of type `string` because we 'decoded it' to 'utf-8' (which is the 'encoding' of text that supports most human languages). If we hadn't decoded it, the result would have been of type `bytes` which wouldn't be easy for us (humans) to work with.</div>\n",
    "\n",
    "Now that we've read our data _as text_, we can print it to check. But since it's rather a _lot_ of data to look at (see `print(len(datafile))`) we use the list slice operation here:\n",
    "\n",
    "<div style=\"border: dotted 1px green; padding: 10px; margin: 5px; background-color: rgb(249,255,249);\"><i>Hint</i>: Remember that you can treat strings <i>as lists</i>, so in when we <tt>print</tt> below we cut off the output at 600 characters.</div>"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "print(len(datafile))\n",
    "print(datafile[:600])"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "So this is definitely text, but it doesn't look like the [data we see at the URL itself](https://github.com/jreades/i2p/blob/master/data/2020-08-24-sample-listings-simple.csv) which has individual data records on each line. To split the text into individual lines, we can use the handily named `.splitlines()` method (more on methods below):  "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "url = \"https://github.com/jreades/i2p/raw/master/data/2020-08-24-sample-listings-simple.csv\"\n",
    "\n",
    "response = urlopen(url)\n",
    "datafile = response.read().decode('utf-8').splitlines()\n",
    "\n",
    "print(\"datafile variable is of type: '\" + datafile.__class__.__name__ + \"'.\\n\")"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Note now, how the _data_ variable has type `list`. So to view the data as we see them in the original online file, we can now use a `for` loop to print out each element of the `list` (each element being a row of the original online file):"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Print the number of rows in `datafile`\n",
    "print(??)\n",
    "# Print the first two rows of `datafile`\n",
    "print(??)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "That's a little hard to read, though something has clearly changed. Let's try:"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Print the last row of datafile\n",
    "print(??)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "The last row should be `40373464,\"Modern, Small Double Private Room\",139052118,Leon,2017-07-07,51.46497,-0.17807,Private room in apartment,Private room,1,,1.0,1.0,$38.00,1,1125,0,4,6`.\n",
    "\n",
    "**Congratulations!** You've now read a text file sitting on a server in, I think, Canada and Python _didn't care_. "
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Task 3.2. Text into Data\n",
    "\n",
    "We now need to work on turning the response we got to our `urlopen` request into useful data. You'll notice that we are dealing with a _CSV_ (Comma-Separated Value) file and that the format _looks_ quite simple... So, in theory, to turn this into data we 'just' need to _split_ the row into separate fields using the commas.\n",
    "\n",
    "There's a handy function associated with strings called `split`:"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "print('abcdefgh'.split('d'))"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "You can also investigate further how the split function works using:"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "help('abcdefgh'.split)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "So this seems like a good solution to turn our text into data:"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "test = datafile[-1].split(',')\n",
    "print(test)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Task 3.3. The Advantages of a Package\n",
    "\n",
    "<div style=\"border: dotted 1px rgb(156,121,26); padding: 10px; margin: 5px; background-color: rgb(255,236,184); color: rgb(156,121,26)\"><i>Stop!</i>: Look closely at the output from <tt>datafile[-1].split(',')</tt>. Can you see some problems if you were trying to treat this as data?</div>\n",
    "\n",
    "```\n",
    "['40373464', '\"Modern', ' Small Double Private Room\"', '139052118', 'Leon', '2017-07-07', '51.46497', '-0.17807', 'Private room in apartment', 'Private room', '1', '', '1.0', '1.0', '$38.00', '1', '1125', '0', '4', '6']\n",
    "```\n"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "There are _two_ problems and _both_ are subtle when you're starting out: \n",
    "\n",
    "1. We are implicitly _assuming_ that commas can only appear at field boundaries (i.e. that they can only appear to separate one column of data from the next). In other words, just using `split(',')` doesn't work if *any* of the fields can contain a comma. Take a moment to think about what `split(',')` does and why the output above points to a problem.\n",
    "2. Also remember that `1` and `'1'` are _not_ the same thing. This is another potential problem that we'll have to deal with eventually, but we're not going to do that today.\n",
    "\n",
    "This is where using code that someone _else_ has written and contributed is helpful: we don't need to think through how to deal with this sort of thing ourselves, we can just import the library that we need and make use of _its_ functionality. I've given you the skeleton of the answer below, but you'll need to do a little Googling to find out how to `\"read csv python\"`. **Note:** We're going to table problem \\#2 for another week, for now just focus on problem \\#1."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "from urllib.request import urlopen\n",
    "import csv\n",
    "\n",
    "url = \"https://github.com/jreades/i2p/raw/master/data/2020-08-24-sample-listings-simple.csv\"\n",
    "\n",
    "urlData = [] # Somewhere to store the data\n",
    "\n",
    "response = urlopen(url) # Get the data using the urlopen function\n",
    "csvfile  = csv.reader(response.read().decode('utf-8').splitlines()) # Pass it over to the reader function\n",
    "\n",
    "for row in csvfile:              \n",
    "    urlData.append( row )\n",
    "\n",
    "print(\"urlData has \" + str(len(urlData)) + \" rows and \" + str(len(urlData[0])) + \" columns.\")\n",
    "print(urlData[-1]) # Check it worked!"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "If it worked, then you should have this output:\n",
    "```python\n",
    "['40373464', 'Modern, Small Double Private Room', '139052118', 'Leon', '2017-07-07', '51.46497', '-0.17807', 'Private room in apartment', 'Private room', '1', '', '1.0', '1.0', '$38.00', '1', '1125', '0', '4', '6']\n",
    "```\n",
    "To you that might look a lot _worse_ that the data that you originally had, but to a computer that list-of-lists is something it can work with; check it out:"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "for u in urlData[:15]:                             # For each row in the first 15 items in list\n",
    "    print(\"The host of '\" + u[1] + \"' is \" + u[3]) # Print out the name and host"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "The advantage of using the `csv` library over plain old `string.split` is that the csv library knows how to deal with fields that contain commas (_e.g._ `\"An Amazing 4Bedroom Home, Central London, Sleeps12\"`) or even newlines and so is much more flexible and consistent that our naive `split` approach. The vast majority of _common_ tasks (reading certain types of files, getting remote files, etc.) have libraries that do exactly what you want without you needing to write much code yourself to take advantage of it. You should always have a look around online to see if a library exists before thinking that you need to write everything/anything from scratch. The tricky part is knowing what words to use for your search and how to read the answers that you find...\n",
    "\n",
    "Let's try this with the 'bigger' data set:"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Get the 'bigger' dataset by following these steps:\n",
    "# download 'bigger' file to a 'data' folder inside your current directory and unzip\n",
    "# download url: https://github.com/jreades/fsds/raw/master/data/clean/2020-08-24-listings.csv.gz\n",
    "\n",
    "## to get your current working directory:\n",
    "## import os\n",
    "## print(os.getcwd())\n",
    "\n",
    "# import csv using pandas to your current working directory (modify accordingly)\n",
    "import pandas as pd\n",
    "\n",
    "df = pd.read_csv(r'/home/jovyan/work/fsds_np/practicals/data/2020-08-24-listings.csv')\n",
    "\n",
    "# covert DataFrame to List\n",
    "urlData = df.values.tolist()\n",
    "\n",
    "# insert dataframe columns' Names as a list\n",
    "urlData.insert(0, df.columns.tolist())\n",
    "\n",
    "# print(urlData[:2])\n",
    "\n",
    "# continue with previous code\n",
    "\n",
    "print(\"urlData has \" + str(len(urlData)) + \" rows and \" + str(len(urlData[0])) + \" columns.\")\n",
    "\n",
    "for u in urlData[:10]:                                  # For each row in the list\n",
    "    print(\"The host of '\" + u[4] + \"' is \" + str(u[9])) # Print out the name and host (indices 4 and 9 in this dataset)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "The first row of output should be: `The host of 'name' is host_name`."
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Task 3.4. Hmmmm, is this efficient???\n",
    "\n",
    "So, although the code was basically the same for both of these files, we ended up needing to change the parameters in order to print out the _same_ information from different versions of the _same data_. So our code isn't very flexible... it's rather brittle.\n",
    "\n",
    "One of the issues is that our _instincts_ about how to manage data doesn't align with how the computer can most _efficiently_ manage it. We make the mistake of thinking that it seems like we need:\n",
    "\n",
    "1. To keep the rows in order\n",
    "2. To keep the columns in order\n",
    "\n",
    "So if we wanted to do that then the 'right' data structure would clearly be a list-of-lists (LoLs!). But if you understand what happened here then the next section will make a _lot_ more sense!"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## Task 4. Why 'Obvious' is Not Always 'Right'\n",
    "\n",
    "But you need to be careful assuming that, just because something is hard for you to read, it's also hard for a computer to read! I've said before that the way a computer 'thinks' and the way that we think doesn't always line up naturally. Experienced programmers can think their way _around_ a problem by working _with_ the computer, rather than against it.\n",
    "\n",
    "Some issues to consider:\n",
    "\n",
    "- Is the first row of data _actually_ data, or is it _about_ data?\n",
    "- Do we really care about column _order_, or do we just care about being able to pick the _correct_ column?\n",
    "\n",
    "Let's apply this approach to the parsing of our data..."
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### What's an _Appropriate_ Data Structure?\n",
    "\n",
    "If you stop to think about it, then our list-of-lists approach to the Airbnb data isn't very easy to navigate. Notice that if the location of the description or name column changes between different versions of the file (as it did... deliberately), then we need to change our program _every_ time we re-run it! Also remember that we in order to work out the answer to a simple question such 'what is the average cost of an Airbnb venue' the we need to step through a lot of irrelevant data as well: we have to write a `for` loop and then step through each row with an 'accumulator' (somewhere to store the total). So it's error-prone and it's slow. \n",
    "\n",
    "That doesn't make much sense since this should all be _easier_ and _faster_ in Python than in Excel, but right now it's _harder_, and quite possibly _slower_ as well! When you get into situations like this (having to write a lot of code to do something that should be fast and easy) it is often the case that you've got the wrong _data structure_. So how does the experienced programmer get around this? 'Simple' (i.e. neither simple, nor obvious, until you know the answer): she realises that the data is organised the wrong way! We humans tend to think in rows of data: this apartment has the following _attributes_ (price, location, etc.), and that the shared room has a different set of attributes. Se we read across the row because that's the easiest way for us to think about it. But, in short, a list-of-lists does _not_ seem to be the right way to store this data!\n",
    "\n",
    "Crucially, a computer doesn't have to work that way. For a computer, it's as easy to read _down_ a column as it is to read _across_ a row. In fact, it's easier, because each column has the same _type_ of data: one column contains names (strings), another column contains prices (integers), and other columns contain other types of data (floats, etc.). Better still, the order of the columns often doesn't matter as long as we know what they are called: it's easier to ask for the 'description column' than it is to ask for the 6th column since, for all we know, the description column might be in a different place for different files but they are all (relatively) likely to use the 'description' label for the column itself.\n",
    "\n",
    "##### A Dictionary of Lists to the Rescue\n",
    "\n",
    "So, if we don't care about column order, only row order, then a dictionary of lists would be a nice way to handle things. And why should we care about column order? With our CSV files above we already saw what a pain it was to fix things when the layout of the columns changed from one data set to the next. If, instead, we can just reference the 'description' column then it doesn't matter where that column actually is. Why is that? \n",
    "\n",
    "Well, here are four rows of data from a list-of-lists for city sizes:\n",
    "\n",
    "```python\n",
    "['id', 'Name', 'Rank', 'Longitude', 'Latitude', 'Population'], \n",
    "['1', 'Greater London', '1', '-18162.92767', '6711153.709', '9787426'], \n",
    "['2', 'Greater Manchester', '2', '-251761.802', '7073067.458', '2553379'], \n",
    "['3', 'West Midlands', '3', '-210635.2396', '6878950.083', '2440986']\n",
    "```\n",
    "\n",
    "Here's how it would look as a dictionary of lists organised by _column_, and _not_ by row:\n",
    "\n",
    "```python\n",
    "myData = {\n",
    "    'id'         : [1, 2, 3],\n",
    "    'Name'       : ['London', 'Manchester', 'Birmingham'],\n",
    "    'Rank'       : [1, 2, 3],\n",
    "    'Longitude'  : [-0.128, -2.245, -1.903],\n",
    "    'Latitude'   : [51.507, 53.479, 52.480],\n",
    "    'Population' : [9787426, 2705000, 1141816],\n",
    "}\n",
    "\n",
    "```\n",
    "\n",
    "What does this do better? Well, for starters, we know that everything in the 'Name' column will be a string, and that everything in the 'Longitude' column is a float, while the 'Population' column contains integers. So that's made life easier already. But let's test this out and see how it works."
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Let's apply what we've just learned above. This next section is the _really_ crucial bit. This is going to take time to make sense, but if it does then 🤯!"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "myData = {\n",
    "    'id'         : [0, 1, 2, 3, 4, 5],\n",
    "    'Name'       : ['London', 'Manchester', 'Birmingham','Edinburgh','Inverness','Lerwick'],\n",
    "    'Rank'       : [1, 2, 3, 4, 5, 6],\n",
    "    'Longitude'  : [-0.128, -2.245, -1.903, -3.189, -4.223, -1.145],\n",
    "    'Latitude'   : [51.507, 53.479, 52.480, 55.953, 57.478, 60.155],\n",
    "    'Population' : [9787426, 2553379, 1141816, 901455, 70000, 6958],\n",
    "}\n",
    "\n",
    "print(myData['Name'])"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Now let's look at what you can do with this... but first we need to import one _more_ package that you're going to see a _lot_ over the rest of term: `numpy` (Numerical Python), which is used _so_ much that most people simply refer to it as `np`. This is a _huge_ package in terms of features, but right now we're interested only in the basic arithmatic functions: `mean`, `max`, and `min`."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Find the population of Manchester.\n",
    "pop = myData['Population'][ myData['Name'].index('Manchester') ]\n",
    "print(f\"Manchester's latitude is {pop}\") # Notice how 'f-strings' work!\n",
    "\n",
    "# Find the easternmost city\n",
    "city = myData['Name'][ myData['Longitude'].index( max(myData['Longitude']) ) ]\n",
    "print(f\"The easternmost city is: {city}\")\n",
    "\n",
    "# Print the location of Lerwick\n",
    "city = \"Lerwick\"\n",
    "print(f\"The town of {city} can be found at \" + \n",
    "      f\"{abs(myData['Longitude'][myData['Name'].index(city)])}ºW, {myData['Latitude'][myData['Name'].index(city)]}ºN\")\n",
    "\n",
    "# Find the mean population of the cities\n",
    "# using a handy package called numpy\n",
    "import numpy as np\n",
    "mean = np.mean(myData['Population'])\n",
    "print(f\"The mean population is: {mean}\")"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "There's a _lot_ of content to process in the code above, so do _not_ rush blindly on if this is confusing. \n",
    "\n",
    "<div style=\"border: dotted 1px rgb(156,121,26); padding: 10px; margin: 5px; background-color: rgb(255,236,184); color: rgb(156,121,26)\"><i>Stop!</i>: Look closely at what is going on. Try pulling it apart into pieces and then reassembling it. Start with the bits that you understand and then <i>add</i> complexity.</div>\n",
    "\n",
    "We'll go through each one in turn, but they nearly all work in the same way and the really key thing is that you'll notice that we no longer have any loops (which are slow) just `index` or `np.<function>` (which is _very_ fast). "
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### The Population of Manchester\n",
    "\n",
    "The code can look pretty daunting, so let's break it down into two parts. What would you get if you ran just this code?\n",
    "```python\n",
    "myData['Population'][1]\n",
    "```\n",
    "Remember that this is a dictionary-of-lists (DoL). So, Python first looks for a key named `Population` in the myData dictionary. It finds out that the value associated with this key is a _list_ (`[9787426, 2553379, 2440986]`). In this example, it just pulls out the first value (index 1), which is `2553379`. Does **that part** make sense?\n",
    "\n",
    "---\n",
    "\n",
    "Now, to the second part:\n",
    "```python\n",
    "myData['Name'].index('Manchester')\n",
    "```\n",
    "\n",
    "Here we look in the dictionary for the key `Name` and find that that's _also_ a list (`['London','Manchester','West Midlands']`). All we're doing here is ask Python to find the index of 'Manchester' for us in that list. And `myData['Name'].index('Manchester')` gives us back a `1`, so _instead_ of just writing in a `1` to `myData['Population'][1]` we can replace it with `myData['Name'].index('Manchester')`! Notice the complete _absence_ of a for loop?\n",
    "\n",
    "Does that make sense? If it does then you should be having a kind of an Mind-Blown moment because what we've done by taking a column view, rather than a row view is to make Python's ``index()`` command do the work for us. Instead of having to look through each row for a field that matches 'Name' and then check to see if it's 'Manchester', we've pointed Python at the right column immediately and asked it to find the match (which it can do very quickly). Once we have a match then we _also_ have the row number to go and do the lookup in the 'Population' column because the index _is_ the row number!"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### The Easternmost City\n",
    "\n",
    "Where this approach really comes into its own is on problems that involve maths. To figure out the easternmost city in this list we need to find the _maximum_ Longitude and then use _that_ value to look up the city name. So let's do the same process of pulling this apart into two steps. Let start with the easier bit:\n",
    "```python\n",
    "myData['Name'][0]\n",
    "```\n",
    "That would give us the name of a city, but we don't just want the first city in the list, we want the one with the maximum longitude. To achieve _that_ we need to somehow replace the `0` with the _**index of the maximum longitude**_. Let's break this down further: \n",
    "1. We first need to _find_ the maximum longitude.\n",
    "2. We then need to _find_ the **index** of that maximum longitude.\n",
    "\n",
    "So Step 1 would be:\n",
    "```python\n",
    "max_lon = max(myData['Longitude'])\n",
    "```\n",
    "Because the `max(...)` helps us to find the maximum longitude in the Longitude list. Now that we have that we can proceed to Step 2:\n",
    "```\n",
    "myData['Longitude'].index(max_lon)\n",
    "```\n",
    "So now we ask Python to find the position of `max_lon` in the list. But rather than doing this in two steps we can combine into one if we write it down to make it easier to read:\n",
    "\n",
    "```python\n",
    "myData['Longitude'].index(\n",
    "    max(myData['Longitude'])\n",
    ")\n",
    "```\n",
    "There's the same `.index` which tells us that Python is going to look for something in the list associated with the `Longitude` key. All we've done is change what's _inside_ that index function to `max(myData['Longitude'])`. This is telling Python to find the _maximum_ value in the `myData['Longitude']` list. So to explain this in three steps, what we're doing is:\n",
    "* Finding the maximum value in the Longitude column (we know there must be one, but we don't know what it is!),\n",
    "* Finding the index (position) of that maximum value in the Longitude column (now that we know what the value is!),\n",
    "* Using that index to read a value out of the Name column.\n",
    "\n",
    "I _am_ a geek, but that's pretty cool, right? In one line of code we managed to quickly find out where the data we needed was even though it involved three discrete steps. Think about how much work you'd have to do if you were still thinking in _rows_, not _columns_!"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### The Location of Lerwick\n",
    "\n",
    "Lerwick is a small town in [the Shetlands](https://www.shetland.org/), way up to the North of mainland U.K. and somewhere I've wanted to go ever since I got back from [Orkney](https://www.orkney.com/)--but then I spent my honeymoon in the far North of [Iceland](https://www.westfjords.is/), so perhaps I just don't like being around lots of people... 🙃\n",
    "\n",
    "Anyway, this one _might_ be a tiny bit easier conceptually than the other problems, except that I've deliberately used a slightly different way of showing the output that might be confusing:\n",
    "```python\n",
    "# Print the location of Lerwick\n",
    "city = \"Lerwick\"\n",
    "print(f\"The town of {city} can be found at \" + \n",
    "      f\"{abs(myData['Longitude'][myData['Name'].index(city)])}ºW, {myData['Latitude'][myData['Name'].index(city)]}ºN\")\n",
    "\n",
    "```\n",
    "The first thing to do is to pull apart the `print` statement: you can see that this is actually just two 'f-strings' joined by a `+`--having that at the end of the line tells Python that it should carry on to the next line. That's a handy way to make your code a little easier to read. If you're creating a list and it's getting a little long, then you can also continue a line using a `,` as well!\n",
    "\n",
    "1. The first f-string\n",
    "The first string will help you to make sense of the second: f-strings allow you to 'interpolate' a variable into a string directly rather than having to have lots of `str(x) + \" some text \" + str(y)`. You can write `f\"{x} some text {y}\"` and Python will automatically convert the variables `x` and `y` to strings and replace `{x}` with the _value of `x`_ and `{y}` with the _value of `y`_. \n",
    "\n",
    "So here `f\"The town of {city} can be found at \"` becomes `f\"The town of Lerwick can be found at \"` because `{city}` is replaced by the value of the variable `city`. This makes for code that is easier for humans to read and so I'd consider that a good thing.\n",
    "\n",
    "2. The second f-string\n",
    "This one is hard because there's just a _lot_ of code there. But, again, if we start with what we recognise that it gets just a little bit more manageable... Also, it stands to reason that the only difference between the two outputs is that one asks for the 'Longitude' and the other for the 'Latitude'. So if you can make sense of one you have _automatically_ made sense of the other and don't need to work it all out.\n",
    "\n",
    "Let's start with a part that you might recognise:\n",
    "```python\n",
    "myData['Name'].index(city)\n",
    "```\n",
    "You've _got_ this. This is just asking Python to work out the index of Lerwick (because `city = 'Lerwick'`). So it's a number. 5 in this case. And we can then think, 'OK so what does this return:\n",
    "```python \n",
    "myData['Longitude'][5]\n",
    "```\n",
    "And the answer is `-1.145`. That's the Longitude of Lerwick! There's just _one_ last thing: notice that we're talking about degrees West here. So the answer isn't a negative (because negative West degrees would be _East_!), it's the _absolute_ value. And that is the final piece of the puzzle: `abs(...)` gives us the absolute value of a number!"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "?abs"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### The Average City Size\n",
    "\n",
    "Here we're going to 'cheat' a little bit: rather than writing our own function, we're going to import a package and use someone _else's_ function. The `numpy` package contains a _lot_ of useful functions that we can call on (if you don't believe me, add \"`dir(np)`\" on a new line after the `import` statement), and one of them calculates the average of a list or array of data.\n",
    "```python\n",
    "import numpy as np\n",
    "mean = np.mean(myData['Population'])\n",
    "```\n",
    "This is where our new approach really comes into its own: because all of the population data is in one place (a.k.a. a _series_ or column), we can just throw the whole list into the `np.mean` function rather than having to use all of those convoluted loops and counters. Simples, right? \n",
    "\n",
    "No, not _simple_ at all, but we've come up with a way to _make_ it simple."
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Task 4.1 Brain Teaser\n",
    "\n",
    "Why not have a stab at writing the code to print out the _4th most populous_ city? This can _still_ be done on one line, though you might want to start by breaking the problem down:\n",
    "1. How do I find the _4th_ largest value in a list?\n",
    "2. How do I find the _index_ of the 4th largest value in a list?\n",
    "3. How do I use that to look up the name associated with that index?\n",
    "\n",
    "You've already done \\#2 and \\#3 above so you've _solved_ that problem. If you can solve \\#1 then the rest should fall into place.\n",
    "\n",
    "<div style=\"border: dotted 1px green; padding: 10px; margin: 5px; background-color: rgb(249,255,249);\"><i>Hint</i>: you don't want to use <tt>&lt;list&gt;.sort()</tt> because that will sort your data <i>in place</i> and break the link between the indexes across the 'columns'; you want to research the function <tt>sorted(&lt;list&gt;)</tt> where <tt>&lt;list&gt;</tt> is the variable that holds your data and `sorted(...)` just returns whatever you pass it in a sorted order <i>without</i> changing the original list. You'll see why this matters if you get the answer... otherwise, wait a few days for the answers to post.</div>"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Print out the name of the 4th most populous city-region\n",
    "\n",
    "print(\"The fourth most populous city is: \" + str(city))"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "The answer is Edinburgh."
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "#### Recap!\n",
    "\n",
    "So the _really_ clever bit in all of this isn't switching from a list-of-lists to a dictionary-of-lists, it's recognising that the dictionary-of-lists is a _better_ way to work _with_ the data that we're trying to analyse and that that there are useful functions that we can exploit to do the heavy lifting for us. Simply by changing the way that we stored the data in a 'data structure' (i.e. complex arrangement of lists, dictionaries, and variables) we were able to do away with lots of for loops and counters and conditions, and reduce many difficult operations to something that could be done on one line! "
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "### Bringing it all together...\n",
    "\n",
    "Conceptually, this is one of the hardest practicals in the entire term because it joins up so many of the seemingly simple ideas that you covered in the previous praticals (and Code Camp, if you did it) into a very complex 'stew' -- all our basic ingredients (lists, dictionaries, etc.) have simmered for a bit, been stirred up together, and become something entirely new and more complex.\n",
    "\n",
    "So if this practical doesn't make sense to you on the _first_ run-through, I'd suggest going back through the second half of the practical _again_ in a couple of days' time -- that will give your brain a little time to wrap itself around the basics before you throw the hard stuff at it again. _Don't_ panic if it doesn't all make sense on the _second_ runthrough either -- this is like a language, you need to practice! With luck, the second time you went through this code a little bit _more_ made sense. If you need to do it a third time you'll find that even _more_ makes sense... and so on. "
   ]
  }
 ],
 "metadata": {
  "anaconda-cloud": {},
  "kernelspec": {
   "display_name": "Python 3 (ipykernel)",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.9.6"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 4
}
