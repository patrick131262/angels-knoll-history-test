Now I'll talk about our second workflow, which is built around Claude. 

We chose Claude for two main reasons.
The first is depth. Claude is very good at reading long source document, like a full set of council meeting records or a museum report that runs dozens of pages, and then answering very specific questions about them.
The second is execution. Claude can connect directly to the tools we work in and can actually operate Rhino and Grasshopper. which I want to focus on today.

Like in the GPT workflow, the real architectural potential here is the connection with Rhino and Grasshopper. But Claude takes it one step further. In the GPT workflow, AI turns our ideas into code, and we bring that code into the software ourselves. With Claude, AI works inside the software. It can go straight from a description in words to geometry in Rhino, or to a working component setup in Grasshopper.
That changes how fast we can test ideas. Instead of building every option by hand, we can describe a massing, a column grid, or a parametric element, and see it in the model within minutes. It can also take over repetitive tasks like arraying elements, naming layers, and grouping objects, so we can spend more time comparing options.
how I set up the connection. It takes four steps.
Step one: install the RhinoAI MCP plugin in Rhino. its a receiver on the Rhino side. It lets Rhino take commands from outside and opens up its modeling and Grasshopper functions.(a universal connector between AI and software, 
Step two: install Node.js. This is a runtime environment. It runs the small "bridge" program on my computer that links Claude and Rhino.
Step three: edit Claude's config file. Adding the MCP to the config is basically telling Claude, "There's a copy of Rhino on this computer that you can use."
Step four: run the MCP. Once I restart Claude, it can see Rhino's functions and use them.
MCP stands for Model Context Protocol. 


Once it was connected, I started with a simple test. I asked Claude to build a box in Rhino, and it worked.
Then I tried something a bit more complex: a column grid. I asked for six rows of ten columns, spaced five meters apart and ten meters tall. Each column was a steel I-beam, simplified into three boxes, using any common standard section size. Claude generated the whole grid directly in Rhino.

Then I had an idea: could Claude generate a rough massing model of a real building? So I asked it to model the Absolute World towers. It takes a minitue to searched online and found the towers' rotation angles, estimated the floor plate shape from the photos it found, and then rebuilt the towers in Rhino. We could see it sorted everything into layers on its own, with separate layers for floor slabs, glazing, the core, and the podium, and it grouped each tower separately.

I also tested whether Claude could work in Grasshopper. I asked it to make an I-beam with adjustable length and section dimensions.
As you can see in the video, it built the whole set of components right on the Grasshopper canvas and wired them together. I can use the sliders on the left to change the dimensions.

Here is the biggest difference between the two workflows.
In the GPT workflow, GPT can write the code for a Grasshopper component,. I copy the code, paste it into a Python component, and run it myself.
In the Claude workflow, the AI operates the software on my computer directly. It builds the model in Rhino and connects the components in Grasshopper. My job is to review the results and make the decisions.

Claude also has clear limitations, and a couple of them happen to be GPT's strengths.
First, it can't generate images. GPT can produce concept images and diagrams directly. Claude can only analyze images, or draw simple graphics with code.
Second, it doesn't have the same project continuity as our GPT workflow. We've been using GPT since our first year, so it has built up a lot of context about our work and knows us well. We only started using Claude recently, so it doesn't have that history, and we have to give it the background each time.

So to sum up: GPT is better at going broad. It organizes large amounts of information, keeps track of the overall direction of the project, and produces images quickly.
Claude is better at going deep and getting things done. It reads source documents closely and works directly inside Rhino and our files.



ComfyUI is a node-based AI image generation and workflow tool. Unlike tools like Midjourney, where you mainly enter a prompt and receive an image, ComfyUI breaks the generation process into different nodes and allows you to control how they connect and interact. In this sense, it works almost like a visual programming system, where each node performs a specific task. This makes the process more controllable, customizable, and repeatable.
In architecture, I think ComfyUI is more useful as a design exploration tool rather than simply a rendering tool. For example, I can export a model or line drawing from Rhino or Grasshopper and bring it into ComfyUI. Using tools such as ControlNet, I can preserve the basic geometry and composition while exploring different facades, materials, environments, or architectural languages. I can then evaluate the results, select certain ideas, modify them, and bring the design back into Rhino or Photoshop. This creates an iterative workflow between modeling, AI exploration, and human decision-making.
However, ComfyUI also has some limitations. AI-generated images do not always follow architectural geometry accurately, especially when dealing with complex spaces, structures, or details. The results can also be unpredictable, even with similar inputs. Another limitation is the learning curve. Because ComfyUI gives users so much control, you need to understand different models, parameters, and nodes in order to build an effective workflow.
So, I see ComfyUI as a visual exploration layer within the architectural workflow, rather than a replacement for precise modeling and design tools. Rhino gives me control over geometry, while ComfyUI gives me controlled but exploratory visual possibilities.