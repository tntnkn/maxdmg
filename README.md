# maxdmg
Transform your table graph representation into state machine able to process user input into `docx` document.

The project consists of several independent parts:
1. [maxdmg_resource](https://github.com/tntnkn/maxdmg_resource) will pre-process table representation of user interaction graph into internal form and parse it for errors;
2. [maxdmg_back](https://github.com/tntnkn/maxdmg_back) is the heart of the system -- it turns internal representation made by [maxdmg_resource](https://github.com/tntnkn/maxdmg_resource)  into a state machine that keeps track of multiple users' states and inputs;
3. end users interact with the system via front ends that live completely separately from the other parts of the system. Current front ends are:
	* [maxdmg_tgfe](https://github.com/tntnkn/maxdmg_tgfe) -- Telegram Messenger bot.
4. when end user reaches one of the end states via front end, [maxdmg_docgen](https://github.com/tntnkn/maxdmg_docgen) generates the final instance of the document based on the user's input and exact path that they followed during interaction with front end. These instances are made on the bases of a single template -- [maxdmg_back](https://github.com/tntnkn/maxdmg_back) remembers user's choices during session and then provides them to [maxdmg_docgen](https://github.com/tntnkn/maxdmg_docgen) to determine the final look of the document;
5.  when interaction graphs grow large it becomes increasingly harder to maintain and develop a product -- [maxdmg_portal](https://github.com/tntnkn/maxdmg_portal) provides capabilities for visual presentation of a graph so teams responsible for developing exact generators may see all the branching and outputs of the generator.
