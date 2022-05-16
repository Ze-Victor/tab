<script>
  import { Meta, Template, Story } from "@storybook/addon-svelte-csf";
  import Buttons from "./buttons.svelte";
</script>
<Meta
  title="Tab/Button"
  component={Buttons}
  argTypes={{
    onClick: { action: "onclicked" },
  }}
/>

<Template let:args>
  <Buttons {...args} on:click={args.onClick} />
</Template>

<Story
  name="Primary"
  args={{
    buttonText: "Button",
  }}
/>
