Jul 29, 2025
How to Get Functional 🦾👀 in Cursor 🧠💉 - Transcript
00:00:00
 
Jonathan Penwood: All right, just some housekeeping things. Um, I was making this presentation up until uh like right before this, so it's not complete. Um, at the end, I'll probably just wing it. Uh, but this is as far as as I was able to get today. Um and yeah so and this is also my first time going through it after kind of writing the presentation. So uh just for context and everything. Um but yeah, so the goal of this um this kind of demo is to kind of get everybody to go through a process where everybody kind of downloads Cursor. Um and then after everybody downloads Cursor, we kind of uh go through it together. Um I'll I'll be I'll have cursor up and everything kind of explain some things and then um I'll kind of go through the uh difference between cursor rules and cursor documents and how that applies to the usage of cursor and uh then we're going to go into kind of a workflow um of using cursor. So um the idea is to kind of replace Google search for kind of deep research tasks.
 
 
00:02:41
 
Jonathan Penwood: Um and then uh after that if we have time I I I haven't uh timed this yet so I'm not sure but we'll see. Um the goal is is that we'll try to solve we'll each kind of individually try to solve a problem using cursor and then um try to generate rules and docs and um kind of go through an iterative cycle together of doing that, encountering problems, talking about it, kind of working through things together. Um, and yeah, I I want to spend as much time on the actual like everybody trying to solve problems with it and working on it, but I'm not sure how much time we'll have. I might need to rush through some things and um but yeah, feel free to interrupt though um if I'm going too fast through things or if you have questions um about anything. Okay. So, to start it out, kind of doing a bit of a human prompt. Um, so one of the things about this technology is it's it's pretty new. Uh, a lot of people don't have context for it and um, also just using a new app can be, you know, a process in and of itself, especially one as complicated as cursor.
 
 
00:04:05
 
Jonathan Penwood: So please uh make sure to ask the dumb questions. The problems you encounter um are not just helpful uh to get resolved for yourself but also for everybody else. So all right so this is where the audience participation section begins. Um is there anyone who hasn't downloaded cursor yet before jumping on this call?
Michael Raeder: me.
Jonathan Penwood: Perfect. Um, I messed up the slides.
Steven Levin: I'm currently downloading it also and I have to wait until I get admin rights to my laptop from sec ops before I can install it.
Jonathan Penwood: Gotcha. That is fair. I'll try to get these on the screen for you guys. Um, so, uh, while you're installing, I'll kind of talk about what I put together. Um, and let me make sure I've pushed everything out cuz like I said, I was working on this right up until um just so you guys can have everything. Um, but this should be a good starting point and it'll be helpful in the process of explaining how the tool works.
 
 
00:05:45
 
Jonathan Penwood: Um but yeah so now this uh repo it's a public repo and um it uh yeah it should um it should be accessible to everyone. Um you can just run this get clone whenever you do get cursor installed um in the terminal to get that folder local. And then this is the folder we'll be working with to uh working uh on together uh both for explaining things as well as just kind of giving you a general outline that I found to be effective. Um, yeah. I wish I had more time to like refine these for you guys, but this is this is as far as I was able to get. So, um, does anyone else need the download or GitHub link? Um, that is on the screen.
Bracey Summers: the GitHub link, please. If you can put it
Jonathan Penwood: All right. Yeah, I will grab that for you. It's over on the right. Here we go. All right. So, it's posted in the chat. Um, while you guys are working on that, just kind of an interesting side note, I've been using voice control with uh like using LLMs like just natively from the uh like Mac OS.
 
 
00:07:35
 
Jonathan Penwood: They have like a voice control thing. Um, and it's nice whenever you're like having to type out long prompts just to be able to kind of use natural language to to speak things through. But um for anyone curious, I would recommend looking into it because I found that to be pretty useful.
Bracey Summers: Sorry, what were you using exactly?
Jonathan Penwood: Uh it's a Mac OS voice control. So, uh yeah, it's built into Mac.
Bracey Summers: Is that built in or is that something
Jonathan Penwood: Um it's also Windows has their own uh builtin. Um, but this just like a shortcut or with you can do like um like a specific like um like Alexa phrase basically.
Stacy Jones: You didn't say anything.
Jonathan Penwood: I I was hesitant to say Alexa, but you know how it goes.
Bracey Summers: Is that as good as something like Whisper AI or or some of the other ones that like that?
Jonathan Penwood: Oh, no. It's it's it's not it's not actually like there. It's just like voice to text and then like navigation.
 
 
00:08:31
 
Bracey Summers: Okay.
Jonathan Penwood: Um, so it's it's pretty bare bones, but I found it useful with LLMs because yeah, not every I mean cursor doesn't have a voice feature that I've been using that I'm aware of. It might actually have one by this point, but I'm just oblivious of, but I do find actually just like speech to text directly can be a bit uh bit easier to keep track of things um when like using cursor. So, all right.
Joshua Mix: Hey John, do you know the do you know the current status of how threat connect as a company use cursor and if we may get our company funded accounts and all of that at some point or
Jonathan Penwood: Yeah, I know it's been brought up uh to the executive team. Um I'm not sure what the status is yet on it. Um, I've kind of been heads down in code for basically since the last meeting.
Joshua Mix: Yeah.
Jonathan Penwood: So, up until today, I I uh I haven't really done much followup.
Joshua Mix: Yeah.
Jonathan Penwood: Um, yeah.
Joshua Mix: The thing is I've been kind of hesitant to get invested in any one tool.
 
 
00:09:43
 
Joshua Mix: Um although I have to varying degrees got invested into cursor and cloud code and Gemini. But uh there's just so much config for all of these things at least config.
Jonathan Penwood: for sure. And that's part of the reason like part of the reason that I organ like I'll I'll kind of show as I go through, but one of the things that I think is really important is that none of the things that I teach you about how to use cursor here are specific to cursor outside of the UI. So, I'm going to go through the UI and cursor and like show everybody kind of how to use it. But like every the general like workflows that I talk about or like the rule files or all of that stuff is going to be applicable to any LLM model because really using cursor well I'll get into it. I'll get into it. So um all right.
Joshua Mix: Cool.
Jonathan Penwood: So, does did anybody have any trouble getting cursor downloaded or that GitHub repository installed or is everybody good to go?
 
 
00:10:53
 
Stacy Jones: No. Heat.
Michael Raeder: I'm good.
Jonathan Penwood: All right. So, I'm going to kind of briefly talk about what cursor is um and kind of walk you through how it works. So, cursor is an LLM text editor, meaning you can edit text with an LLM. That's that's all it is. Um in in the tooling of it, it has things to manage context as well. Um that's kind of a concept in and of itself of what cursor is. And then there it it operates almost as a domain knowledge absorber. So as you use it um depending on how you use it, you can um basically absorb domain knowledge while just doing your normal work. Um, and like what does that actually mean practically? So, um, with LLM text editing, that means you chat with an LLM and you, um, create text files using an LLM. You can create or edit them. Um, and with um the ability to um create and edit these files, you also have the ability to manage the context that the LLM is receiving.
 
 
00:12:16
 
Jonathan Penwood: Um, this is useful in a lot of different ways. One is like not having to reprompt over and over to fix like an LLM making a consistent mistake. Um, like links is one example where like links not being good uh like gives you it hallucinates links. you can tell it in a rule to say, "Hey, don't um you know, use links uh that aren't real, like verify every link, and it will actually do that for you." Um so it as a context manager, it allows you to not have to reprompt LLMs over and over and over for doing specific kinds of tasks. Um and then with the domain knowledge absorber, um yeah, so you kind of have to incursor it it it's pretty bare bones. it doesn't force you to uh keep track of things. It just gets rid of it a lot of the time. Um and so there's prompting strategies that we're going to go through um to basically help you actually know how to uh manage your context over time.
Stacy Jones: All
Jonathan Penwood: Um but yeah, so we prompt um yes whenever we're making corrections, we prompt it and it absorbs our domain knowledge is basically how it goes.
 
 
00:13:30
 
Jonathan Penwood: So um all right, so first thing first, first things first, uh the cursor chat window.
Stacy Jones: right.
Jonathan Penwood: So, I've done my setup pretty bare bones just so everybody can kind of mimic it and then I'll show you some features um around how this works. All right. So, I will just open this read me. So, we have a text file. So, um so there's two modes in which the chat window can operate. One is in this kind of sidemounted window and another is um let me see.
Jonathan Hoye: John, are you sharing your uh text editor?
Jonathan Penwood: Oh.
Jonathan Hoye: I think you might want to swap those.
Jonathan Penwood: Oh, I that yeah I thought I shared my window. I appreciate the call out. Um I switched like desktops on my Mac and I guess it didn't. I guess the presentation did didn't pick that up. Thank you. Thank you. Uh, let's see. Entire screen. Yeah, that that was a mistake. There we go.
 
 
00:14:56
 
Jonathan Penwood: All right. So you can also split out chats to be inside of like actual like text text file tabs. That's another thing. So you can have as many going as you want at once. It's just machine and cost, right? Um, so we'll go through kind of some more of those details like in a bit, but um, one of the the patterns that I like is to have one window down here for general web search and one over here for like actually operating on files like in plans and that kind of stuff. So, um, yeah. Uh, but you can have it sidemount. That should come up uh, by default in sidemount view. Yeah, I believe so. If anybody else is seeing the setting, so like I get it to mount. There's a way. I think I can do it like this actually. If you just go into any file and cursor, you highlight text and you hit command L, it opens up a chat window and adds whatever you highlighted to the context.
 
 
00:16:09
 
Jonathan Penwood: I'll get into more exactly how this chat window works in a bit. Um, but this this can either be kind of locked to the side or windowed. I can't figure out how to get it to lock again because I prefer it to be like actually in its own tab. Um, but yeah, so the chat window is here and then let's talk about prompting strategies and how to actually use this chat. So, um, one of the reasons in terms of window management that I put a chat window in this in in a separate like tab on the side is because whenever you're operating on files like text files in cursor, um, it has to open them up next to the chat window or if it's like mounted, it'll just open a bunch of tabs up like in your actual like usable space. So, it's best to, in my opinion, have it like this. So, when it's operating on files, it just opens them next to it in this kind of uh panel. Um, and that's one of the reasons for having it windowed as well.
 
 
00:17:18
 
Jonathan Penwood: Um, you can see at the bottom here, you have the history of your chats. You can also access the history of your chats by hitting command shiftp um and typing in history. Uh, let's see. Yeah, there it is. It's right at the bottom. Show chat history. And then you can go through here and search if you want to see more than like what's here. I think you can also just click this. So you can find it in the command shift P or in the actual just click that. Um or if you want to go back to one, you can just click it. it'll have everything that you had in that time uh with what you were doing. So, I'll get into how the chat features work really quick. Um, works like pretty much any other LLM in terms of the text box. Um, there's a few things down here to talk about. Um, most people are probably aware of this idea. Um, but there is times in which you do not want it to edit files.
 
 
00:18:23
 
Stacy Jones: There he is.
Jonathan Penwood: Um, and that's when you put it into ask. If you don't want it to edit files, make it ask. Um, also ask tends to give more concise quick answers even with like the more extensive models I found. So, um, sometimes it is best to go to agent just ask a question and be really explicit about it, not changing anything. Um, but yeah, so agent is mainly for changing files. ask is for mainly like, you know, doing searches or that kind of stuff. Um, down here is the model selector. Um, I'll switch mine to auto. So, everything I'm doing is should be matched in terms of behavior. Um, and there's also this little context thing here. So, I talked about um how this is a context management app, right? It helps you manage context with LLMs and this is one of the mechanisms you can use to do that. Um, a few things to highlight. Uh, docs are really important to using this tool.
 
 
00:19:32
 
Jonathan Penwood: You will be making a lot of your own docs if you use this tool at all. Um, so docs are indexed documents that come from URLs. So if you want to add a new one, you just go to the bottom, click add new doc. you know, have a uh URL and then you can give it a name and it will basically web scrape any website and make a um a rag a a portion of its rag database now is just that document in cursor. Um, you can you can find the indexed docs by going to your settings and then going to indexing and docs and you can go into here and add or delete as well.
Stacy Jones: Wow.
Jonathan Penwood: Um, this is a really important part of how cursor works.
Joshua Mix: Does that uh have you noticed that eating up a lot of context?
Jonathan Penwood: Um, no. Because uh context docu or because the index documents and how it indexes it uses rag, um, it doesn't seem like it's eating up a bunch more context. More of what it ends up eating up context tends to be these things because you really only use docs to generate other text files and then you operate on those text files.
 
 
00:21:05
 
Jonathan Penwood: So, this is a really important component to using the the platform. Um, but it's not necessarily something you're using every single time that you are chatting. Um, because you basically use them one time and then generate documents using them for your purposes.
Joshua Mix: Okay.
Jonathan Penwood: Um, uh, they're I I call them plan files, but some people call them spec files. Um, but we'll kind of get into that uh further on. So, but yeah, you can add your own documents, any website, any URL. Also, if you go on Google and you search and you find like a forum or something, it's really good with forums. Like it it it ends up generating much higher quality stuff with uh with indexing forums over a lot of other things. So, yeah. Um with that in mind, I'll go back. Make sure I'm staying on track. Cursor settings. Okay, we're just there. So here, so I would recommend that you kind of leave everything default um as you're using the tool and just change settings as you get annoyed.
 
 
00:22:14
 
Jonathan Penwood: Um that's that's what I did and it tends to work pretty well. Most of the most interesting settings are inside of this chat here. Um that's where you can have it, you know, like stop at the end of every single thought or, you know, not have access to the terminal or other kinds of things. um you know you can kind of work on how much you trust the tool to do specific things. Um there are things in which you definitely should not trust it. So you know be careful and stuff but uh but yeah in general um as long as you know what you're doing it's not going to do anything uh majorly weird or mess up your machine in any way. Like it's not going to do anything outside of the context of the folders that you have inside of the actual like window. Um, with that in mind though, if you do have like other folders in the same window, it sometimes gets confused. So, like what I have right here is a workspace. So, you can rightclick on the bottom and click add folder to workspace and it will, you know, bring up a window where you can select anything and add it to the workspace.
 
 
00:23:22
 
Jonathan Penwood: So, you can add more than one folder separately. Um, however, that is something that I have seen it have difficulty with in the past. So, um, but yeah. So, I think that's everything. Now, we can get into the actual folder structure and how this thing works a little bit. Um, so yeah. um whenever you're chatting with this thing um it is not much better than the model that you're using. So if you were to copy and paste all your code into chat GPT um and like you know ask it to do something it would give similar results because it's you know a lot of the time just using the chat GPT model that you would just copy and paste it into right but that's not where the power of this tool comes from. It's not the um the models or the LLMs being particularly awesome or whatever it is. It's actually kind of how you manage the context around the LLM um in order to get it to achieve the purposes you're attempting to get it to achieve, right?
 
 
00:24:35
 
Jonathan Penwood: Um which is just editing text files, right? Because it's that's all it does. So um with that in mind, there are two kind of folders in here. you'll see one and they're both underneath this cursor folder. So cursor uses this folder um to manage context um around different tasks that you're doing. Um I use these docs um in order to like manage my specific project. So if I'm working on like a specific integration um the docs will have like things that are specific to the integration. Um, and then I'll get into transcripts later. Um, then rules. So, we have these rule files. So, rule files have a different uh file type. They're MDC. That's how cursor distinguishes them between being rules versus documents. Um, and so you can have a rule reference a document. So, you don't necessarily need all of the text that you need like in here. You can like link things inside of these documents. Um, you can reference other documents.
 
 
00:25:44
 
Jonathan Penwood: So like for example here I had it when it generated this um add markdown linking. So whenever you click on you know this link it shows you hey this is related to this other rule. And so with markdown linking, you can effectively um basically minimize your context window uh by having a rule set that's minimal um that's always on and then having it dynamically traverse the links um is something I found to be helpful for minimizing context with rules and such. So I'm going to get back to this Yeah.
Joshua Mix: Hey John, real quick the so is there a way on Gemini like the CLI tool you can run it in debug mode and it'll tell you everything that it loads into the context up front. Can you do that with cursor? Like are you sure that it's not going into all these links at the very beginning? Just curious.
Jonathan Penwood: Yeah. So, I mean, I haven't done extensive testing. I I just noticed my context windows go down when I started to use that.
 
 
00:27:02
 
Jonathan Penwood: So, it's very anecdotal in terms of what I'm saying there. Um, in terms of uh the way that I use this tool, um, I get what you're I I have the feature implemented um, using cursor rules. So that's one of the things about cursor is cursor is very design agnostic and it wants you to tell it what you want. So I have like for example um uh tracking manual rules. So these are rules that you have to manually put into the chat. These are rules that were always on and that's decided at the top of the file right here. Anytime you have a MDC, this little thing appears at the top of cursor and you can uh tell it uh how to apply it. So really though between there's only really two because if you click this it you know it just changes this to false. So I mean I think there might be other stuff behind the scenes in cursor. So but from a objective like when a person loads in your file it just loads manual or always on.
 
 
00:28:09
 
Jonathan Penwood: Um, and so all those other things are nice if you want to set them, but they're not extensible to a team because those things are not tracked in the configuration at the top of these rule files. Um, and so this manual tracking, let's see, transcript formatting here. This is what I was trying to get at. So, um, I have a rule that I use, um, to basically have, uh, transcript files, um, inside of my documents. And I get basically time travel level chat logs on each problem I'm working in with like timestamps and you know every single uh line change. I'm just tracking everything right now. Eventually I'll probably minimize that but they're transcripts so I'm not operating over them. I'm just adding to them um using this rule set. So I don't need to like load in the whole file to just add to the end of it you know. Um and so I get similar level in terms of the debug um with I would say this transcript formatting agent rule that I have in the repo.
 
 
00:29:13
 
Jonathan Penwood: Um, yeah, because it's so agnostic, they just they want you to tell it's basically any feature you want in a text editor.
Joshua Mix: Cool. Yeah.
Jonathan Penwood: It can probably do like not necessarily any, but you know, I don't know how much is moving around buttons, but honestly, like I'm planning on using this to generate extensions um like for for VS Code or for cursor, so that way I can have basically a rule set that allows me to actually physically change the UI whenever I want to. um because it it literally has that level of, you know, access. You just would need to, you know, if you wanted to change the UI very directly, you'd have to get into um building your own extensions, which are pretty simple. But um but yeah, does that kind of answer your question, Josh?
Joshua Mix: Yeah. Yeah, for sure. I've just I've noticed like I've added rules and I'm probably just doing it incorrectly, but sometimes they don't always seem to be applied even though I have it on always apply.
 
 
00:30:02
 
Jonathan Penwood: Right.
Joshua Mix: So, I just would like to see what it's actually loading.
Jonathan Penwood: Oh yeah.
Joshua Mix: But, but it's cool. I mean, I can
Jonathan Penwood: Yeah. No, it is the always on is I try to keep those more general conversational um gen like very context that I might reference every once in a while but the always on does not always get added. It tries to do it intelligently like it tries to basically make um I think something along the lines of an MCP server for navigating these when you say always on um I think that's what's probably going on behind
Joshua Mix: Okay.
Jonathan Penwood: the scenes is it's basically making its own um dynamic usage of the always on. So there are times in which I actually do put the always on files in inside of the chat um if it's getting something wrong that is covered in these um for sure.
Bracey Summers: Hey John, is that that directory structure you have under rules is that standard or is that something you did and it's just recursive?
Jonathan Penwood: So um so rules is something that's specific to cursor and so is docs.
 
 
00:31:20
 
Jonathan Penwood: Everything else inside of rules is whatever you want. Um, and this read me is optional. Like the only you don't even need rules or docs or the cursor folder to use it. It's just these are these are the structures that cursor uses at the top level and then everything inside is custom to what I how I've kind of been finding it to be useful kind of in a in a minimal way.
Bracey Summers: Okay. Yeah, that's what I was I understood the rules director, but the always on and the manual tracking folders, that's all stuff you you created and cursor.
Jonathan Penwood: Yeah, I made that for the purpose of uh because like they there's a lot of I I basically what I did was a while back uh whenever I first found cursor and then saw how useful it was. I went on GitHub and found like top five 10 cursor rules repos and just kind of analyzed the meta principles of those and then tried to apply them to actually building something. And this is what's spat out of that.
 
 
00:32:16
 
Jonathan Penwood: Um, you know, with probably about 20 minutes of generation like because I I didn't have much time to get this repo fully fleshed out, but I did like curate it and make sure it's this is this is the legit stuff that is actually working for me. So, um, but this is a distinction that I'm making is always on or manual. Uh, a lot of people organize it differently. Um, but this is, I think, like an MVP structure for pretty much solving any problem, no matter how extensive, um, with the tool. Um, yeah.
Bracey Summers: Got you.
Jonathan Penwood: Are there any any other questions u from what we've been talking about so far? All right. So, let's talk about really what is the difference between rules and documents. They're both markdown files. Um, however, rules are basically how you correct cursor, how you teach it to not do something. And documents are more of uh like positive, you know, context you're giving it, I would say. um just things that it needs to know in order to operate in your domain and edit the files you want to edit appropriately.
 
 
00:33:28
 
Jonathan Penwood: Um, and so, um, the reason that you need these rules are that these LLMs make mistakes all the time, and especially at the beginning when you first get started in these things, uh, even with cursor, it's going to give you a lot of crappy answers, but um, you kind of have to tell it what you want in a way that sticks around. That's kind of a big part of actually making the tool work and be able to do kind of almost like kind of be an everything tool uh for text editing. Um is you kind of have to tell it what you want in a specific way. Um and so domain context is important because LM's don't have context on your specifics and they will go to the most general possible answer if you don't give them specifics. Um, and so you the the use of cursor in terms of how do you actually like use these rules or use these documents and actually like go about creating them for yourself, for your own domain, for your own context, uh, for your own use cases is we just create markdown files, right?
 
 
00:34:32
 
Jonathan Penwood: Um, we create markdown files and then we refine those those markdown files um to kind of get the crap out and get the good stuff in. And that's kind of how it works is basically generating these markdown files as you're using the tool um to customize the feature set to your domain and use case. Does that kind of all make sense?
Joshua Mix: Yep.
Jonathan Penwood: All right. All right. So, we're going to get into a workflow really quick. Um so workflows in cursor can be manual or automated. Um the basic idea is is that um you can use a um a process of prompting. So it's not just how can I make this one prompt give me the best answer. It's a sequence of prompts that you know you're going to be giving to it um in order to solve a problem. And so you break it down into smaller pieces and you try to apply um a sequence of prompts over an individual prompt just giving you what you want right out of the right out of the gate.
 
 
00:35:45
 
Jonathan Penwood: So and that's a big part of the prompting strategy with cursor is keeping it very conversational, keeping it very fluid um and then g creating the rigidity you need inside of document files. Um so that way you actually can fully flesh out your ideas and really brainstorm with the with cursor um on the ln side and then um after brainstorming you can refine files down then actually start using those files to do what you want to do. um it is kind of a step in the middle and it is a slowdown at the beginning but I think right away you'll you'll find these you'll these these uh rules that I've made here in the structure already probably improves the tool a decent amount. So um at least for me it has uh because these are just kind of copied and pasted from other files that I've done before. Um so at web so cursor allows you to add context through this context window here. Um, you can add libraries, you can add forums, you can add anything you want there.
 
 
00:36:52
 
Jonathan Penwood: You can also specifically call out rules. Hey, I want you to make sure to add whatever I'm saying here to the transcript. Um, and I have that set to like a manual rule, so I can do it kind of incrementally in batches. Um, and you can add things there, but you can also hit the at sign and you get the same window inside of the chat. So you can do the exact same thing inside of here. One of the tools that you can add to context is web. So web basically just, you know, does web scraping. Whenever you add it to the context, it will go on the web and scrape whatever you want. Um, and what the workflow I'm going to kind of walk you through today, um, uses, um, kind of a specific strategy that takes advantage of the, um, let's see, there we go. Got that pasted for you guys. um if you want to do the exact same or just you know change it for whatever you're uh trying to actually do.
 
 
00:38:06
 
Jonathan Penwood: Um so the idea is is that uh for this workflow to replace Google is you use the at web in your prompt so that way it searches the web and you tell it to give you various amounts of links in different ways. So you say, "Hey, give me three different links uh that are verified working." You know, make sure to tell it that um you know uh and to uh links to resources on how to make pancakes, right? So that's the example that I'm putting here. Um and you can specify what you want the links to be. So you can say make two of the links blog recipes with high organic ratings on the recipe and make one of the links a forum on how to cook pancakes in various ways. So when I go on web and paste that prompt into here, what I get in response pretty quickly, well maybe not maybe not as quick. Maybe I'm being a bit uh optimistic. There we go. Perfect. So now I have three copyable links that I can go into here and say add docs and go to the bottom.
 
 
00:39:28
 
Jonathan Penwood: Add new doc. Paste. And this says Reddit, but I'm going to say uh pancakes. All right. So now I have pancakes added to the context that link. Um so I found three is a pretty good sweet spot um depending on the problem and the scope of what you're trying to tackle um whether it be code or anything else. Um but now I have that document and um I can basically use that uh that index document to ask questions now. So by adding these links to your index documents and then adding them to context, the quality of the answers you get out out of it end up going up immensely. Um and you don't want I I think I mentioned before like I'm not uh using these context documents like all the time. I just use them for kind of the initial setup stuff. Um, but now that I have that pancakes expert uh link, we can um now that we've indexed those links uh and we've gone through uh and added it to the chat, um we can prompt it again.
 
 
00:40:47
 
Jonathan Penwood: And let's give this to you guys so you guys can follow along. So this is an example of like a manual workflow that I did purely manually, right? Um, and now that I've done this, um, it's giving me ingredients to make it from scratch, you know, and now in terms of the results, it's still an LLM. That's one thing to always keep in mind with this. This is still an LLM. It still makes stuff up. It still hallucinates. It still makes mistakes. Always be very skeptical of the answers it gives. However, I can have more confidence in this answer um because I added this index document and in general over doing this many many times I found that doing this process this meta workflow kind of thing manual workflow u works really well and now that I have this manual workflow I've done it what I can do is is I can say make me a cursor rule that if applied um does the link context getting process I just did good.
 
 
00:42:37
 
Jonathan Penwood: So this kind of gets to the first lesson of prompting with it um now that I'm actually kind of using it for something a little more complicated. Right? So, I've done this process manually. And the thing with cursor that's really awesome is uh because of its context management, it's kind of solved transfer learning. Um I'm not sure if you guys are familiar with the general problem of transfer learning, but it's a big one and it's kind of solved with this. And so what you can do is you can take what you've done in a manual conversation and turn it into a rule set. So it always does the same thing when you apply that conditional rule. So um in doing so though one of the things about cursor is if you give it a relative path it will mess up um very consistently I found that I tried to add rules to make that stop. It does not stop. I cannot add relative paths to this thing. I just have to add like full paths.
 
 
00:43:32
 
Jonathan Penwood: So how I do that is I just go rightclick on the folder um that I want to reference and I've also found adding uh files through highlighting in this way is not not as effective. Um I found full file paths it just works consistently. Trying to fix that has been just a colossal waste of time for me. So, I would suggest at least for the time being until unless you you find a way around it because I tried a few things and it was really annoying. Uh, but until then, I'm just personally copying the entire path because it gets confused really easily if you don't do that. Um, and then um let's see. So I said uh make me a cursor rule that if applied does the link context getting process I just did um yeah let's say and one of the things about it is so I mentioned full links the other thing is I kind of have a prompting strategy that I use on basically every prompt. Uh the first thing is I kind of give it a general gist of what I want it to do.
 
 
00:44:42
 
Jonathan Penwood: um I reference things with full paths and then I tell it what I don't want it to do and then I tell it what I want it to do. So it's kind of I just have to make sure that I tell it not to do things because otherwise I'll forget and then it'll do something. So whether that's adding a rule, whether that's explicitly telling it not to do something. Um uh like for example here I I have uh a rule I want to say uh don't edit any files in this folder but create a new rule. So it's a positive case a negative case and in the positive case what I'm actually going to do is I'm going to add an index doc. I've already kind of done this before. or cur the cursor forum honestly is one of the best things I've found for generating rules. Um their like website's really easy to find find the forum and everything else like they have a bunch of documents that are kind of optimized for the purpose of using it this way.
 
 
00:45:40
 
Jonathan Penwood: Um, but yeah, so you can I'm adding the cursor forum and then I want to say use the cursor forum to make sure this rule works and is concise. So you'll see it ran a curl request and then you can see it creating the rule file and and after it creates it I'll have to accept the file changes since it you know changed some file and you can accept them line by line inside of the file. or in this case it's just one big change because it's just created a new file. Um, and so I'm going to keep and I've noticed something. It generated, but it added this down here. So, I want to move that. I have to do some manual changes because it broke. It's already set to manually apply, but I'm just going to change it back and forth. So, it um adds it up at the top and then you save. Anytime you change this, it does change the text of the file. So, you do have to save.
 
 
00:47:13
 
Jonathan Penwood: So, I fixed that little mistake it made. And now I have a rule that apparently will give me pretty good links. So I can now instead of um instead of retelling it the same prompt, I can say at link context gathering and I can say um uh give me five links on snowboarding. And now I get very nice, concise answers, answering the exact same way without having to tell it to verify links, without having to tell it to do all this other stuff. And so this is an example of a way you can use cursor to build your own workflows is you have chats with it. You use the chat that you had to transfer learn that information into a rule set and then you can apply the rule without having to reprompt in the same fashion and it saves you a bunch of time. U does anyone have questions about the process up to this point? This little workflow I'm showing.
Jonathan Hoye: I have a question. I kind of lost you when you were setting the context at the at pancakes point up at the beginning.
 
 
00:48:35
 
Jonathan Penwood: Yes.
Jonathan Hoye: Did you do anything before actually just typing that in and adding some text after it?
Jonathan Penwood: Yeah. So what I did was um I did at and then docs because whenever you hit at you can add like rules or docs the same way as you do there but it's just inline. So I click that. If you go to the bottom of this you just hit the up arrow it says add new doc. And whenever you add a new doc it automatically just pops populates here. So whenever I added that link, that's why it started showing pancakes right after automatically right after I added it, even though it kind of seemed a bit sudden.
Jonathan Hoye: Got you.
Jonathan Penwood: But in general, it'll just look like this. It'll have this highlight. It'll add it up to here for you. But being able to reference things in line, I found to be generally fruitful. So I try to use inline context as much as possible. Um, it just prevents a whole class of problems that the tooling has.
 
 
00:49:30
 
Jonathan Penwood: So yeah.
Jonathan Hoye: Cool. Would you be willing to copy and paste your prompt for generating that doc?
Jonathan Penwood: Um let's see.
Jonathan Hoye: I started taking notes. I was like, this is a lot of stuff, but this is really a good example.
Jonathan Penwood: Yeah. Yeah. Luckily it's I'm recording too, so we'll be able to kind of reference back later. Um yeah, I don't know. I don't think we're actually going to get to everybody working on their own problem separately and and chiming in, but with the time because there is I guess more than I thought uh to cover. So, but any other questions in terms of what I did around the um the asking it for three links, doing kind of a manual workflow, and then turning that into a rule. Um does anyone have any questions about that? All right. Oh, sorry. Might have jumped a gun. All right. Cool. So um the same thing I did with these um documents in terms of I added them to the context and generated use used them to generate uh you know a better response or a more uh trustworthy response right you can do the same with documents.
 
 
00:51:02
 
Jonathan Penwood: So, um let's say um h does anyone have like a tool that um that they use day-to-day that I probably know nothing about
Joshua Mix: That's really hard to answer. I don't know what you know.
Jonathan Penwood: like a a scripting language. I guess we can do bash or or something else, but I'm thinking if there's like a a question that you guys have that I can kind of do for you and then turn that into a doc the the kind of expert document instead of using the documents directly is my thought. But um I mean that's that's basically it works the exact same way with these. However, when you add the context, your goal isn't to generate a rule. So you the context you add is more around what kind of documentation you want. Um so I have like organized transcripts for my projects. Um these are the three that I use um like all the time. So like anytime I have a meeting like I can add Gemini meeting transcript notes here and then use this tool to generate in my opinion much better scoped uh summaries than what Gemini can just off the bat because Gemini is you know general purpose but you can use this tool to like take your transcripts and actually like say hey give me these five scopes in the summary and then it'll take that information and then you can
 
 
00:52:34
 
Jonathan Penwood: tell it to you know link docs to you have everything kind of connected and so you can like verify it the docs that it comes up with um so it links out to the actual index docs like the actual routes and everything so you can verify it with real world information whenever you generate documents but just to save time I think I'll I'll forego that process um uh okay so that was one example of a workflow um oh I think Yeah, that was as far as I got in making the presentation. So, I I do have a plan of where where to go from here. Um, so let's see. Yeah, I think we got kind of some of the meta information kind of documented and flushed out. Um, so where I wanted to go from here is talking about plans, plan files and transcript files and why they're useful in cursor specifically because basically that transfer learning capability allows you to have it generate basically these plan files like uh task files, spec files, they're called a bunch of different things on a bunch of different repos.
 
 
00:53:52
 
Jonathan Penwood: Um, and that is in my opinion the key to making this thing do crazy things. Um, because in order to make this do really complicated tasks and make it not spiral off into like a corner and not work, um, it needs direction. And rather than you prompting it with that direction every single time you see it veering off, you can tell it to generate a plan with checkboxes, um, with kind of details, with file references, with anything that you need for it to operate. And then you say, hey, let's execute on this plan and check off the check boxes as you go. Um, and that is, I would say, where the power of this tool is. It's it's a useful LLM tool in and of itself with what I've shown you so far. The rules, the documents, it's going to be, you know, it's going to be better than any LLM tool that you can use in terms of fitting the answers to your use case and having trustworthy answers. Um, but if it if you give it too abstract or large of a task, it doesn't work.
 
 
00:55:05
 
Jonathan Penwood: Like that's just how it is. Um, I think that's how it is with basically all of these tools. Um, and that's why I think these plan files, having these things execute on pan files isn't unique to cursor. Um, this is something that all like LLM CLIs are kind of doing in a way. Um, there's a lot of things like clawed taskmaster. Um, is one that kind of is built around this idea of these plan files. Um, and yeah, so I'll kind of get a little bit into that uh really briefly. Um, does anyone have any questions up to this point though about what I'm talking about with these plan files or task files or that kind of stuff?
Joshua Mix: I mean I I I run into issues when I'm having it selfiterate on a problem like I tell it this is the input I expect this output fix this code path you know and that could be multiple files
Jonathan Penwood: Yeah.
Joshua Mix: um I guess maybe you'll get into this in the plans but that's one of the trickiest problems like I have to babysit it because if I step away and it self iterates a lot.
 
 
00:56:12
 
Jonathan Penwood: Yeah.
Joshua Mix: Uh, you know, a hallucination will end up in one of those iterations and then it'll just compound and then it'll solve a completely different problem than what I wanted. I assume plans can help with with that kind of Okay.
Jonathan Penwood: Yeah. that that is exactly what they prevent because that is in my opinion where where a lot of the seeming impressive stuff we see on demos and videos and different things. The the way that they're actually able to do that is basically these context files. I'm talking about like I mentioned rules and and docs, but generally speaking like these task plan files, they're they're pretty ubiquitous. So much so that cursor is integrating this idea into their UI. This was an update they did about a week ago um where they added to-dos and check off to-dos so it keeps track of what it's doing better when it's doing more complicated tasks. And um so like this principle, this kind of meta principle of making a having it generate a document that you can verify and make sure it doesn't veer off beforehand.
 
 
00:57:21
 
Jonathan Penwood: That's a big thing. The other thing that's really important to put into your plans is very specific and strict realworld criteria and definitions of done. That's super important. So, inside of I have a rule that I put in the manual here for you guys' use um called plan generation. And this is what I use to generate my plans. Um there might be some integration specific stuff. I'm not sure. Uh, I think I had it filter it all out, but not certain. But basically, this is what I just add this rule to context. Um, I say at plan generation.mmdc and I say, um, I usually actually use whenever I'm doing plan generation, I'll usually actually use the voice feature. Let me see if it works while I'm on the call. I would like you to update. Okay, it's working. Okay, so I'm just going to voice type this out real quick. Just really quick example. Um, I want you to make a plan for um revamping every file in this folder.
 
 
00:58:50
 
Jonathan Penwood: So, it's still listening and I'm talking and so it's probably going to keep Yep, it does that. One of the joys of using voice to text and not wanting to turn it off. Funny. Um, I want you to make sure that all of the uh files inside of this folder are extremely uh wellverified in terms of links. There is inline linking on every single one of these documents for other uh documents that are being referenced. And I want you to generate the plan file here. So, I'm going There we go. It's easier when you're not presenting to have that happen as much, but it does happen every once in a while. I forget I have it on and it'll type for me. Um, so I have it. So, it's going to generate turn this off really quick. So, not great for presentations. Would not recommend uh after that experience. So, okay, let's see. Wait, how is it? I swore I just turned it off.
 
 
01:00:37
 
Jonathan Penwood: Goodness. Oh, okay. So, I sent it and I realized as soon as I sent it, I forgot to add something to it. So, I just immediately stopped it. It doesn't charge you for doing that. it actually cancels out any charge even if you're using a model that would charge you as you go. So, um canceling out um yeah is good. Um so I want it to also what do I want to say? I want I want to have strict verification criteria. Um, every link should either be local or have a verified 200 on every inline link referenced. Is this useful? Am I Am I I could have just like doing this thing, but is this helpful to you guys?
Joshua Mix: Yeah, I think so.
Jonathan Hoye: I think it's good. It it I I don't know what kind of questions to ask because I've never really gotten into this type of usage of any of the AI tools. So, it's kind of a good survey just to see what you're doing.
 
 
01:01:57
 
Jonathan Penwood: Yeah. And I and every single time I use it, I'm kind of improving how I use it because of the nature of how I get it to absorb context. And it's just like, yeah, I'm learning new things about it every time I use it, which is great. Um, it's a it's a fun process. Um, but it's also just super powerful. Once we get kind of this plan file, I'll show you how I execute on it. So I have this I can do accept all. So if you uh go into here and hit command enter it just accepts all the file changes. It only added this one file. So it wasn't that much. But that's another way you can accept file changes. Um and it made out of it made out a a plan for me with some checkboxes. Looks like some code. All right. So, uh, basically, and I I'll be able to kind of just start ranting after I get this going, but, um, you know, I copy the whole because it's not a rule.
 
 
01:03:07
 
Jonathan Penwood: Uh, I think there's probably a way I could document with the at sign, but I'm not quick with that. So, I just with documents, I tend to just copy and paste the full path. So I say execute on this plan and make sure to keep it updated as you go with what you verified you completed. Let's see. Yeah, what you've completed. And then I also want to add the transcript transcript formatting agent. Uh create a new transcript file here with time travel level chat logs. Okay. So I said here and my strategy is generally to put it just on a new line a for readability because when you're putting these large paths or these random web URLs in inside of your context can be a bit hard to read unless they're on their own line. So I usually do that this way. And so anytime I say like here I can basically with the voice to text just like speak out the whole thing and then afterwards go back and add all the references.
 
 
01:04:34
 
Jonathan Penwood: So I'm not like doing that all the time. Okay. Transcripts cursor chat. Here it is. So I'm saying I want you to add the transcript to this location and let's see how it goes. Um but yeah like I found with these uh plane files like executed in this way and you have to babysit at times but the gap of babysitting can be anywhere from like 5 to 10 minutes because while this plane is operating you can go and actually just do other work. it doesn't actually require your attention because with this it's um you know with this uh plain file it's going to start executing on certain files right it's going to start I actually gave it the whole entire folder so it's going to execute on everything so I couldn't work on anything else while this is generating but in real code bases you know you have a front end and a back end um and you can just work on you know get the get this specific section of the code with this to like the 80% so my goal goal with this technology is not to get to I have a perfect set of code right out of the gate.
 
 
01:05:45
 
Jonathan Penwood: My goal is that it saves me time by generating to me to the 80% that I need. Um and then that that also by doing that it can generate 80% for anyone. And that's really where I I find this tool exciting and why I I have invested some time into it um is because really at its core Yeah. this can just save you time. Um, it is something that right now based on the studies that I'm seeing and AI coders not actually saving people's time but I don't know how many people are actually like using it in this full fashion either. That study was uh a bit you know you have to isolate variables for studies but it's how it goes but I don't know I don't know uh for now I can tell you for certain that it is slowing me down. um it does slow me down in my workflow because of the level of context that I'm gathering because I want to build a machine that can build all of the apps that I build for my job.
 
 
01:06:45
 
Jonathan Penwood: I think I think that's possible with this technology. It's just a matter of documenting over time varying contexts and then organizing that context memory and then having eight LMS generate to maybe 90 99% or whatever and just a human reviews like I think we can get there with polarity integrations with this tool. Um, and whether it's this tool or whatever other tool, you know, we we all land on, um, this meta process is the thing about cursor that I think is actually powerful and any of these LLM tools. Um, is that kind of creating solutions in just natural language for any problem that you encounter through making it write the actual text. It's like, yeah, I think that alto together along with the transfer learning capabilities would allow for At least for the apps that I'm building. I'm building these small full stack apps, you know, like for my use case, I think I can do that. Um, but yeah, like this is an kind of an everything tool because it's anytime you want it to do something, you just tell it to do it in text in natural language and then refine what it's doing through actually observing it.
 
 
01:07:56
 
Jonathan Penwood: Um, but yeah, that's kind of uh I would say the whole spiel. Um, yeah. What What are you guys' thoughts?
Bracey Summers: It's awesome. I I learned a lot. I need to go spend some time playing around and trying to reproduce some of the things you did. But it is I can see value for sure.
Jonathan Penwood: Yeah. And even if it doesn't get to that full 80% or something, you know, a 60% generation solution is better than writing it all from scratch, you know.
Bracey Summers: Yeah. I think for for us, John, in in the use case of integrations where we're kind of not every integration is the same by by any means, but some of the framework is always the same. Some of the structure that you do is always the same. So, that kind of helps us out. It just can fill in the pieces that are different per integration. That would be super helpful if it could do that.
Jonathan Penwood: Yeah. Well, and that's one of the things, too.
 
 
01:08:50
 
Jonathan Penwood: I can I'm adding a folder right now. I'll show you the last integration that I'm still currently in process on, but it's a it's a good example of kind of how these files evolve in a real project um and what they're useful for. So, let's see. Here it is. So my strategy in the context of polarity integrations is um to have different two different verification methods. So one is 90% test coverage and one is real world scripts that actually go out to the API and run the actual integration functions and verify that they're returning, you know, valid results um uh with log files in this results thing here that's get ignored. And then I have these little docs in here for the scripts to like explain how to use them uh manually for people. Um and then the rules. Um, this is super messy. Um, and not at all what I think it's going to be long term. I've learned a lot since kind of coming up with this. Um, and I kind of just lazily added things to it.
 
 
01:10:14
 
Jonathan Penwood: Uh, which is nice because it can do that. But my plan is, um, to refine the rule set that I made for you guys, uh, based off of this a little bit further. Um, this I found this kind of stuff to be really helpful, giving it context around your your setup and what you want. um other things too, but the setup that I I put in this demo folder is probably the closest uh you know, this demo folder is probably the closest thing to where I'll land on the next integr integration that I work on. And so getting around specifics, so there's general rules that just apply to any kind of use of the tool. And there's ones that are specific to the actual app that you're building. So in Docs, it's also the same, right? I have all my transcripts from all of the generations that I've done. Um, I sometimes have multiple transcripts for each plan file. So, if you get stuck and I have to stop it and have to update the plan file again, that's another part of the process is like sometimes you'll catch it going doing what's in the plan, but you didn't catch before that the plan was actually incorrect.
 
 
01:11:13
 
Jonathan Penwood: And so, you'll stop it, tell it to update the plan file, and then go again and, you know, update with anything that it didn't actually do. Um, real world verification is, in my opinion, the biggest pain point for me at this point with integrations, but um, I I'm trying to make it more automated. So I have one here like a just a document file that I'll add whenever I'm working on stuff that's like really particular to our framework. Um and so I've generated kind of how I want integrations file structure folder structure um use cases like uh scope of each file that kind of stuff uh is all kind of diagrammed out here. And so this is like all integrations generally speaking you know would probably fit this pretty well. And then um here are the plan files in case you wanted to scan. But um I also have these docs around the specific API.
Bracey Summers: Do you know?
Jonathan Penwood: So I have the schema, the GraphQL schema. I have uh PRD that's specific to this project uh that I use and aid with generating plans to be in scope with the broader goals.
 
 
01:12:15
 
Jonathan Penwood: Um sorry ask your question. I uh I'm kind of just going on and on.
Bracey Summers: No, no, just real quickly on on the if I remember like when I was first starting to look at cursor and I had not spent that much time on it at all, but I understand the the docs and the the rules um there's a hierarchy there where you can do I don't you know like can you do like rules in your home directory like you know user bomeverscursor rules that are general okay but you can do
Jonathan Penwood: No, it won't. Cursor won't pick those up. Uh I believe I tried it.
Bracey Summers: it in nested folders is that correct?
Jonathan Penwood: Correct. You can do them in any level nested inside of the main structure folder.
Bracey Summers: And how does it how does it treat those rules?
Jonathan Penwood: So post.
Bracey Summers: Is it like the the closest to the source wins or is it adds them all together or
Jonathan Penwood: So, uh rules um so there you know manual and automatic right.
 
 
01:13:01
 
Jonathan Penwood: So, um actually I think I'm need to scroll up here. So, uh we have manual and always on. So, always on rules are, like I mentioned before, my speculation. I haven't dug into exactly how it's using them because it doesn't use the rule files that are always on every every chat. It does not do that. I've confirmed that for sure. And so, um I don't know exactly how it's using these, but my guess is it's probably create like adding these to some sort of rag database and then referencing them conditionally based on what you're asking in the prompt. And then the manual rules, you know, they're never added to context. So you only add these manually to context. They're never just automatically added to context.
Bracey Summers: Yeah. So I was curious like for some of the projects we have, we have Python code and then we have Angular code but they're in separate directories. So would it make sense to do docs and rules at the nested uh level for the language so that when
 
 
01:13:57
 
Jonathan Penwood: Yeah. I think what I'm finding in terms of structure is simplicity is best. So mi if you mimic the structure that might add some complexity that would add to the context and limit the quality of your results. And so um like I think in my mind, um you can document that like in the sense of how I did here. Um I would say put putting those in document files and not rule files. And then with the framework stuff um I think that like in terms of what would be equivalent for you um and in your integration context this um this integration framework.mmd. So that would be more of like a document kind of a problem in my mind. It's it's not necessarily a clean separation because rules are just more strictly held. But generally speaking, whenever I want to give it context on like a proprietary framework type of thing, I I'd go to documents. So I'd have a document for the Angular side and a document, you know, like kind of have documents for the different um sections of the app and then reference those documents in order to generate a rule um is probably how I would go about working through that.
 
 
01:15:12
 
Bracey Summers: So I I guess you know my naive thought process on this is documents are more um knowledge for it to understand the context of everything and rules are more instructions on what to do. Um does that make sense?
Jonathan Penwood: Yes.
Bracey Summers: Okay.
Jonathan Penwood: Yes.
Bracey Summers: So, does it when it does it pick up the documents from the top level and apply it as you're working on a source file? Like if I'm 10 levels deep into a project and working on a file, does every document above that part get picked up? And does that cause it confusion? Would it make more sense to have the document at the closest level to the place I'm working on if it's only relevant to that code?
Jonathan Penwood: So it does. So manual rules and documents are never added to context unless you specifically add them. So this docs folder might be indexed in terms of how cursor just generally indexes all your code, but in terms of what you use in the in these files. It doesn't add them to context unless you explicitly add them or it's added to like the window context.
 
 
01:16:12
 
Jonathan Penwood: So like I think it might do this. It might show you how this works here. So see it says here three files and so it tells you the context of the changes it's made in certain certain times. But sometimes it also when whenever you have a tab next to it, it'll have it just automatically added in context like if that's part of your chat and it'll kind of keep these uh as reference. whatever's next to it kind of stays as reference if you want it to be more automatic. Putting those files next to the chat like in the same panel will get you like it to reference that. I'm not exactly sure how, but I've definitely seen that before where just having these things up here has them added to the context as it operates. it will add to the context with plan files um like inside of the your panel and then from there you can see everything that's being added to context uh directly or you can remove things you know and you can say hey don't don't reference any of these things only reference this you can tell it what you want and don't want it to look at um sometimes you have to explicitly um uh say again Yeah, you you'll
 
 
01:17:19
 
Bracey Summers: Okay. But none of the documentation is there by default though. None of the documents are there by default though in the context. You you have to add every one of those.
Jonathan Penwood: have to prompt it for specific documents for you to add. Yeah.
Bracey Summers: Okay. I was thinking I don't know why I was thinking that it was it's building some kind of Ryan context and then based on my prompt it was looking up the knowledge it needed.
Jonathan Penwood: For your domain.
Bracey Summers: But I guess that's not
Jonathan Penwood: Not with the planning. So like with the planning like it goes through these phases. Let me see if I it shows it in this chat. Then we can review what this plan did. We I wasn't looking at it at all. So we just kind of let it go. And great real life use case. Right. So at the beginning of this prompt, you know, it creates the transcript for me that I mentioned.
 
 
01:18:12
 
Jonathan Penwood: Um let me see. But you see kind of each of these reads whenever it's actually playing out these. Let me see. Can you expand these a little bit? Yeah, you can expand and see more. Oh, no. I didn't even know that was a thing. You could add a chat to the middle of discovering things on the on the demo. This is cool. So, apparently you can go into the middle of its responses. I thought that might expand it out and show its reasoning, but basically you can read the reasoning as it's going um in these kind of grayed out areas. But um yeah, does that kind of answer your question?
Bracey Summers: Okay. Yeah.
Jonathan Penwood: Okay.
Bracey Summers: Thank you.
Jonathan Penwood: Um all right, let's see see what it did and then discuss. Um okay, so I mentioned before adding new folders to the workspace sometimes get it gets it confused. So um I see it added Oh, no, no, no, it did not add.
 
 
01:19:16
 
Jonathan Penwood: Okay, it did not make that mistake in this this specific instance. It made that mistake a little bit earlier today when I was generating this folder. So, um I I thought it might have done it again. So, it says that it's updated the readme. So, let's just go to get to actually view these changes and I can show you guys what it did. So, it made these changes to the read me. It I guess yeah, it changed the folder structures to be correct. They were incorrect before. All of that looks correct to me. Uh, rules. Okay. Updated this to have links in it. It didn't have links before. So, now these are like markdown links. So, I can just click this whenever I'm looking at the markdown and it'll bring me to the place it's referencing and it itself would be able to hypothetically reference it. Same thing here, just more added links and more fixing of the paths. So, this one's good.
 
 
01:20:31
 
Jonathan Penwood: This is just a brand new file. Um, I liked how it gave me more links, so I'm going to add it. And here uh looks like it's probably more path updates. And now basically I think most of what it updated with the execution of the plan seems to be um these path updates. So if I see anything that's out of the ordinary of that, this is just a new file. It's an execution of that plan. So you'll be able to kind of see what the plan file was and what it did in this generation. So, one of the things you'll notice is the check boxes are not checked on all of it. So, it does pause in the middle of doing the plans. It does however much it thinks it can do with the context window you give it based on the model and does as much as it can. But you'll notice it says validation checks. All external links are tested, right? It hasn't done this yet. Um, and so that's important to keep track of is when you're running with your plan files, it seems like, oh, it's done.
 
 
01:21:35
 
Jonathan Penwood: it it you know in this case it's really nice and it told me oh yeah there's more stuff to do but um you know sometimes it says it's done and it's not done so it's important that you review the plan files make ask it to update the plan files with uh verified results um before checking things off like that kind of stuff um is really important when evaluating your your kind of iteration on the plan files because the plan files are not static like I said sometimes you realize in the middle of it running that I've made mistakes so you stop it and you update the plan file So you iterate on the plane file. Um, and so in here we have this uh transcript and I can show you what that transcripts look like, what that transcript looks like based on kind of what I uh what kind of scoped summaries I wanted to have on my chat uh chats. So um let's see. We get these, we get these, and that's it. So that's by default what we're getting, but you can add other scopes.
 
 
01:22:36
 
Jonathan Penwood: So sometimes what I have it do is I add a scope to the summary for a specific transcript um where it is I tell it to uh have a scope for what rule improvements it could make in the future um to make it so I don't have to reprompt it over and over for the same things. So like I have that as a part of my transcript stuff. um generally speaking whenever I'm running these and then it I mentioned the time travel level transcripts when actually going through and this is what it spits out. It's by no means perfect. Um there's plenty of improvement that's possible on these transcripts to get better summaries and high quality results. But the idea is is that I can in I can use these transcripts all of the transcripts that are inside of um this integration that I built. I can just use all of them to generate updated rule sets and documents for my domain context. So like all of these transcripts are going to be included in the next integration that I build in the context of rules and documents that are actually effective uh versus the ones that I created that I've been using that I've kind of been iterating on but maybe aren't exactly what I want.
 
 
01:23:57
 
Jonathan Penwood: So I can use the kind of the an analysis of the transcripts to find meta patterns that I can create rules from in my domain context. Yeah, but it looks like everything's pretty good in terms of what it did on this generation. Um, so I can push that up.
Jonathan Hoye: John, have you uh looked into configuring cursor to make use of get commits to record your plan steps?
Jonathan Penwood: Uh I've talked with Ed about it before. He was doing that. I forgot what it was a CLI tool that kind of uses Git automatically instead of like the inline references. Um and we talked about it briefly, but I I haven't tried yet. Um, another thing that I'm I like and I really want to get into is like the MCP servers. Um, I want to start because I know cursor has like integration with NC MCP servers that you can reference. So that's another thing too where there's a lot to explore because it really is kind of like an anything tool like you can transfer learning is solved, you know.
 
 
01:25:10
 
Jonathan Penwood: So like it's more of an issue of how creative can you be in figuring out the path to get it to give you what you want more so than can it actually do this is is with a lot of things not necessarily everything but with a lot of things context window is really your only limit. Um so
Jonathan Hoye: A follow-up question of my last one would be to look into the possibility of having the tool look at a series of git commits to learn of a particular type of operation. For example, reconfig if if we're gonna let's say you wanted to refactor an integration's templates to use web components, could you train it somehow based on work done manually to convert those templates or um you know is that something that just has to be done through a series of prompts.
Jonathan Penwood: Yeah, I mean I found that like workflow rules is so like basically where you have it prompt you ends up being pretty helpful like in terms of being able to do it do things in a conversational way with good results.
 
 
01:26:25
 
Jonathan Penwood: Um like you can have it you can literally just tell it hey ask me five questions about this plan uh to make sure you're understanding the scope and the definition of done and all of that stuff. Um, and yeah, um, I'm not sure if I'm Yeah, I think yes.
Jonathan Hoye: I think that touches on some related stuff.
Collin Rogers: I I was looking.
Jonathan Hoye: I'm just curious to know if you can look if you can have the tool reference a series of git commits to learn how your
Jonathan Penwood: Oh, so to to be clear, yes, you can. um like you I haven't explored doing so but I cuz I've been keeping Git pretty separate from the LLM stuff just so I can you know make sure I'm not pushing stuff up uh to public repos that people are using the bugs you know so because I I still don't trust it enough to like just let it let it push to GitHub for me uh in my setting but uh I think I I know for sure it can run git commands like it has uh the ability to like I have to specifically tell it not to commit whenever it gets done with certain things in plans.
 
 
01:27:24
 
Jonathan Penwood: The other thing it's that you can do is GitHub issues. It has pretty good integration with cursor. And so what you can do is is document requirements and GitHub issues and then have cursor pull those in and attempt to, you know, create the 80% solution with background agents and then push the solutions. That's like an available feature right now that they're trying to market quite heavily. Um, so like in terms of git integration, it's pretty solid. Um, so you can kind of have it do like it, like I mentioned before, it's kind of an everything tool. So like if it if you can do something in the CLI, it can do that a thousand times a second. You know what I mean? Like it can it can run as many of those as in parallel, you like. So in terms of git, it just runs everything through the CLI. Um, and you can have rules to dictate when it actually runs those uh commits. And like I know I know with uh with some use cases people are literally like almost every single file change is basically committing automatically be behind uh what what it's doing and then it's has really good tooling around reverting back to other commits really easily.
 
 
01:28:30
 
Jonathan Penwood: Um and I I I believe that's definitely possible in cursor. I haven't tried it but I I believe it's possible with what I've seen it do.
Collin Rogers: I was looking through some of the ways that you can add context to your chat and it looks like there's an option for adding add a get and there's a there's a branch diff with main branch commit diff
Jonathan Penwood: next to your
Collin Rogers: with working state. So it looks like you could in theory um you could compare a working branch or you could compare PR against um your main branch. So if you had a PR that was for just doing one specific feature set and you wanted to create a plan or a task around doing that specific feature set. It sounds like that's what you would want to use.
Jonathan Penwood: Yeah, it's kind of a that's kind of the everything tool of it is kind of figuring out the workflow of prompts to get it to generate good results, you know, and along with the context that's needed. It's it's a process to figure that out and then once you kind of figure that out it gives pretty solid results um in your domain from what I found and integrations is really hard too because we use basically all custom stuff on the front end um that doesn't have really great documentation but it it was able to generate an entire front end for an integration with a lot of bugs but it that 80% it it definitely
 
 
01:29:52
 
Jonathan Penwood: was able to accomplish that for me like you know my first attempt really actually using it to build an integ ation. So, yeah, I'm hopeful. I think that this, you know, it's just going to get better. You know, that's one of the things too with this is that cursor is like one of the top three in the war right now that's going on between all these different, you know, uh trillion dollar companies trying to trying to take all the market share for this stuff. But, uh you know, obviously I'm being a bit hyperbolic. But they they they are competing very heavily and I cursor gets updates like every other day at the least you know like it's updating all the time which is really cool.
Collin Rogers: Yeah, it does seem to have a lot more of a mature feature set to compared Klein. I've been using Klein for some pretty similar stuff and I really like the way that it integrates a lot closer to the UI and cursor. So, I think I'm going to try and use that moving forward.
 
 
01:30:55
 
Jonathan Penwood: Yeah. Well, it's worth giving a shot. I think like I find like what I kind of started with doing was kind of trying to use it directly. Just, hey, fix this file, you know, fix this problem. But yeah, the plan stuff is really really what made it shine for me in terms of the complexity you're able to make it do. Even on the, you know, the standard model, it's able to do some pretty impressive stuff with enough context. So, Yeah. Well, and I I'll uh I'll follow up uh in the AI coders channel, too, um with kind of a an update on kind of where where people are at in terms of uh getting everybody a license for Cursor. Um but yeah, I'll post I'll post an update for that. Um since that was a question. Um because I think I mean right now I'm just paying out of pocket um for it because it's just kind of it a after I've started to use it pretty extensively it kind of seems ridiculous to code in any other way.
 
 
01:32:00
 
Jonathan Penwood: So I'm pretty sure this Yeah, probably that's my assumption but you know it it's I'm fine if it's not.
Collin Rogers: I'm pretty sure this is a reimburseable expense. You are paying for it.
Jonathan Penwood: You know it's it's just that useful for me. I'm Yeah, I'm gaining a lot of value. I'm getting more. It's It's ridiculous the amount of tokens you get. It's just absolutely ridiculous. Like, you get like $6,000 of tokens or something a month for the $200 a month subscription. It's like insane. Um the cost savings compared to just using like direct models and stuff. So the 200 subscription is worth it.
Collin Rogers: Are you doing the the $20 a month or the $200 a month? Do you feel that the added value of the $200 a month subscription is worth it?
Jonathan Penwood: Uh yeah, for sure for me. I mean like the thing is is I basically run everything on max mode now unless it's like a a small question or something smaller. Um, but like my plan files have gotten pretty extensive and pretty trustworthy and so I want to be able to have the results be the highest quality they can with the plan files.
 
 
01:33:14
 
Jonathan Penwood: Um, and so it makes sense for me. Like there's it's like I would say like a 20 to 30% quality bump or again completely anecdotally off of intuition, not actual data, but uh uh but yeah, like that's kind of my intuition is it gives decently better results, noticeably better results uh with the max. And you do have a limit with the 200. It started giving me warnings because I was using it for like everything. So I've been starting to switch back and forth. Um but yeah um for me it's worth it 100%.
Joshua Mix: Yeah, if you use Cloud 4 set through the anthropic API, it eats tokens real quick. I could see you reaching $200 really quickly if you were doing it straight through the API.
Jonathan Penwood: Yeah.
Joshua Mix: Not that I'm paying $200 a month for cursor, but you know
Jonathan Penwood: And and I Yeah. Well, and and the other thing too is like it gives you like the amount of tokens you get is just like insane. like for what you get like uh or for how much you're paying.
 
 
01:34:19
 
Jonathan Penwood: That's the thing about it with like that's what uh Gemini CLI kind of pulled that move too and now cursor is doing the same thing since they were acquired and because they have money now so they can kind of just throw you know an infinite loss of money just at people adopting these things really early now that they have the backing and I think yeah cursor and Gemini CLI are the two that I think are the most value I mean Gemini CLI is like free and they're giving $500 in tokens a day or something like that. It's a crazy.
Jonathan Hoye: This is UI question real quick. Is there an easy way to see what you've used for your whatever your model is that you have running on a chat?
Jonathan Penwood: Um, yeah. So, wait, let's see.
Jonathan Hoye: I'm not finding it as a Click around just anywhere.
Jonathan Penwood: Oh, like in the actual chat history, I believe my Yeah, I think well the model uh if you do auto, it does it switches the model dynamically based on the question that you ask and the amount of like
 
 
01:35:18
 
Joshua Mix: How Look.
Jonathan Penwood: requests you have left on your account. However, you can go into here, you can add models and you can select specific models. Um, but in terms of tracking, let me see if in the transcript it put it in there. Let's give that a shot. Um, probably be at the top. Yeah, I probably would have it if if I wanted that information, I'd probably just add it to just I think I do now that you're mentioning it. Um, add it to the transcript files is probably my solution to that. um like have a little section up here that just says model. I think in other transcripts I might already do that. Um let's see. Yeah. Yeah. In my actual transcripts, I make sure to have that specified. So that's how I keep track of it. Does that uh kind of make sense?
Jonathan Hoye: I think so.
Jonathan Penwood: Cool.
Jonathan Hoye: There's no dashboard. You have to actually configure it to record what it's using and doing.
Jonathan Penwood: Yeah. Yeah. Like I said, it throws away a lot of stuff. Um that's why I started doing these transcript files because it's Yeah. Yeah. All right. Well, I think we're a little bit past past the time on this one, but uh it's been great. Uh any any other questions or kind of action items anybody can think of um that I might be missing or Yeah, for sure. All right.
Jonathan Hoye: It's a great survey.
Jonathan Penwood: Yeah.
Brad Proctor: Thanks all have a good
 
 
Transcription ended after 01:37:56

This editable transcript was computer generated and might contain errors. People can also change the text after it was created.
