<script>
  import { Meta, Template, Story } from "@storybook/addon-svelte-csf";
  import Tab from "./tab.svelte";
</script>
<Meta
  title="Tab/Tab"
  component={Tab}
  argTypes={{
    onClick: { action: "onSelection" },
  }}
/>

<Template let:args>
  <Tab {...args} on:click={args.onClick} />
</Template>

<Story
  name="Primary"
  args={{
    tab: [
        {
            description: 'Texto do Tab 1',
            buttonText: 'Tab 1'
        },
        {
            description: 'Texto do Tab 2',
            buttonText: 'Tab 2'
        },
        {
            description: 'Texto do Tab 3',
            buttonText: 'Tab 3'
        },
        {
            description: 'Texto do Tab 4',
            buttonText: 'Tab 4'
        }
    ]
  }}
/>
