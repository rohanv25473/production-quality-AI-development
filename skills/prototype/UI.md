# UI comparisons

Place variants in the actual surrounding page when there is a natural host: navigation, representative content, and realistic information density help expose tradeoffs. In an isolated prototype checkout, keep existing behavior available. For a new surface, use a clearly named temporary route or standalone preview that follows the project's conventions.

Compare structure, hierarchy, or the primary interaction, not merely colors or wording. Two or three distinct variants are usually sufficient. Let each option differ enough to express its tradeoff rather than forcing all of them into one shared layout.

Use an obvious variant switcher, with shareable parameters such as `?variant=A` where supported. Make the active option clear. Keep experimental controls outside production delivery and avoid keyboard shortcuts that interfere with typing.

Use sample data and temporary state for interactions. Keep real provider writes out of the experiment. Give the owner an accessible preview, a few actions to try, and an explanation of what each variant helps or complicates. Capture which option or combination was selected and why before moving to production planning.

Adapted from [Matt Pocock's UI prototype guidance](https://github.com/mattpocock/skills/blob/main/skills/engineering/prototype/UI.md).
