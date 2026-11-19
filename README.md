# NO MORE AI SLOP

Reusable instructions for projects that need clear English, maintainable Python, consistent document formatting, and well-designed learning materials and websites.

## Use this in another project

1. Copy [AGENTS.md](AGENTS.md) into the new project's root. Copy the guides you need into its `agent_docs/` folder so the relative links work.
2. If the project already has an `AGENTS.md`, merge the shared writing rules and relevant guide links into it. Keep the project's existing build, test, and workflow instructions.
3. Remove rows for any guides you did not copy. Start the Agent task from that project and describe the work normally. The table tells Codex which guide to read.

For example, “Make a six-slide deck explaining the model results” uses the shared writing rules and [LEARNING_STYLES.md](agent_docs/LEARNING_STYLES.md). “Turn those slides into a Word handout” also uses the document formatting in [NOTE_STYLES.md](agent_docs/NOTE_STYLES.md).

Edit `AGENTS.md` for preferences that apply everywhere. Edit the relevant guide for rules specific to one type of work.

## Use your own slide theme

If you want future slides to use a university or personal theme, update `agent_docs/LEARNING_STYLES.md` in that project.

1. Attach your PowerPoint template, a sample deck, or screenshots. You can also paste colour hex codes and say where each colour should appear. Include any required fonts, logo placement, or layouts.
2. Paste the prompt below into your agent chat. Replace the university name and bracketed text with your own details. Remove any line you do not need.

> I’m a Universiti Malaya student. Update `agent_docs/LEARNING_STYLES.md` so future slides follow the theme I provide.
>
> Theme reference: [attached template, sample deck, or screenshots].  
> Colour and font requirements: [background, heading, body text and accent colours, plus font names].  
> Required layouts or logo placement: [add details if applicable].
>
> Use my explicit requirements first and the reference for the remaining design choices. If I only provide colours, keep the current font and layout guidance. If a detail is unclear, keep the current rule and tell me which detail you could not confirm.
>
> Update **Theme and typography** and any related layout or final review rules that mention the old theme. Keep the guidance on meaningful figures, clear writing, and one slide per section when I ask for a compact deck. Edit the Markdown guide directly and summarise the new defaults.
