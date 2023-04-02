<script>
    // import { isActive, url, layout, beforeUrlChange } from "@sveltech/routify";
    import "carbon-components-svelte/css/white.css";
    import {
      Header,
      HeaderNav,
      HeaderUtilities,
      HeaderAction,
      HeaderGlobalAction,
      HeaderNavItem,
      HeaderNavMenu,
      HeaderPanelLinks,
      HeaderPanelDivider,
      HeaderPanelLink,
      SideNav,
      SideNavItems,
      SideNavMenu,
      SideNavLink,
      SideNavMenuItem,
      SkipToContent,
      Content,
      Theme,
      RadioButtonGroup,
      RadioButton,
      Grid,
      Row,
      Column,
      Tag
    } from "carbon-components-svelte";
    import SettingsAdjust from "carbon-icons-svelte/lib/SettingsAdjust.svelte";
    import UserAvatarFilled from "carbon-icons-svelte/lib/UserAvatarFilled.svelte";
    import UserAvatarFilledAlt from "carbon-icons-svelte/lib/UserAvatarFilledAlt.svelte";
    import ChartBar from "carbon-icons-svelte/lib/ChartBar.svelte";
    import Dashboard from "carbon-icons-svelte/lib/Dashboard.svelte";

    let isSideNavOpen = false;
    let isOpen1 = false;
    let isOpen2 = false;
    let isOpen3 = false;
    let theme = "g90";

  </script>
  <Theme bind:theme />
  <style>
      :global(#main-content.bx--content) {
        background: none;
      }
  </style>
  
  <Header company="SDG" platformName="Smart Microgrid" bind:isSideNavOpen>
    <svelte:fragment slot="skip-to-content">
      <SkipToContent />
    </svelte:fragment>
    <!-- <HeaderNav>
      <HeaderNavItem href="panel/dummy" text="Link 1" />
      <HeaderNavItem href="panel/dummy" text="Link 2" />
      <HeaderNavItem href="panel/dummy" text="Link 3" />
      <HeaderNavMenu text="Menu">
        <HeaderNavItem href="panel/dummy" text="Link 1" />
        <HeaderNavItem href="panel/dummy" text="Link 2" />
        <HeaderNavItem href="panel/dummy" text="Link 3" />
      </HeaderNavMenu>
      <HeaderNavItem href="panel/dummy" text="Link 4" />
    </HeaderNav> -->
    <HeaderUtilities>
      <HeaderAction
        bind:isOpen={isOpen1}
        text="Settings"
        icon={SettingsAdjust}
        closeIcon={SettingsAdjust}
      >
      <HeaderPanelLinks>
        <HeaderPanelDivider>Switcher subject 1</HeaderPanelDivider>
        <HeaderPanelLink>Switcher item 1</HeaderPanelLink>
        <HeaderPanelLink>Switcher item 2</HeaderPanelLink>
        <HeaderPanelLink>Switcher item 3</HeaderPanelLink>
        <HeaderPanelLink>Switcher item 4</HeaderPanelLink>
        <HeaderPanelDivider>Switcher subject 2</HeaderPanelDivider>
        <HeaderPanelLink>Switcher item 1</HeaderPanelLink>
        <HeaderPanelLink>Switcher item 2</HeaderPanelLink>
        <HeaderPanelDivider>Switcher subject 3</HeaderPanelDivider>
        <HeaderPanelLink>Switcher item 1</HeaderPanelLink>
      </HeaderPanelLinks>
          
    </HeaderAction>
      <HeaderAction
        bind:isOpen={isOpen2}
        text="User"
        icon={UserAvatarFilledAlt}
        closeIcon={UserAvatarFilled}
      >
      <HeaderPanelLinks>
        <HeaderPanelDivider>Switcher subject 1</HeaderPanelDivider>
        <HeaderPanelLink>Switcher item 1</HeaderPanelLink>
        <HeaderPanelLink>Switcher item 2</HeaderPanelLink>
        <HeaderPanelLink>Switcher item 3</HeaderPanelLink>
        <HeaderPanelLink>Switcher item 4</HeaderPanelLink>
        <HeaderPanelDivider>Switcher subject 2</HeaderPanelDivider>
        <HeaderPanelLink>Switcher item 1</HeaderPanelLink>
        <HeaderPanelLink>Switcher item 2</HeaderPanelLink>
        <HeaderPanelDivider>Switcher subject 3</HeaderPanelDivider>
        <HeaderPanelLink>Switcher item 1</HeaderPanelLink>
      </HeaderPanelLinks>
      </HeaderAction>
      <HeaderAction bind:isOpen={isOpen3}>
        <HeaderPanelLinks>
          <HeaderPanelDivider>Switcher subject 1</HeaderPanelDivider>
          <HeaderPanelLink>Switcher item 1</HeaderPanelLink>
          <HeaderPanelDivider>Switcher subject 2</HeaderPanelDivider>
          <HeaderPanelLink>Switcher item 1</HeaderPanelLink>
          <HeaderPanelLink>Switcher item 2</HeaderPanelLink>
          <HeaderPanelLink>Switcher item 3</HeaderPanelLink>
          <HeaderPanelLink>Switcher item 4</HeaderPanelLink>
          <HeaderPanelLink>Switcher item 5</HeaderPanelLink>
        </HeaderPanelLinks>
      </HeaderAction>
    </HeaderUtilities>
  </Header>

  <SideNav bind:isOpen={isSideNavOpen}>
    <SideNavItems>
      <SideNavLink href="/" text="Dashboard" icon={Dashboard} />
      <!-- <SideNavLink text="Link 3" /> -->
      
      <SideNavMenu text="Charts" icon={ ChartBar }>
        <SideNavMenuItem href="daily" text="Daily" />
        <SideNavMenuItem href="week" text="Weekly" />
        <SideNavMenuItem href="monthly" text="Monthly" />
        <!-- <SideNavMenuItem href="panel/dummy" text="Status" /> -->
      </SideNavMenu>

      

    </SideNavItems>
  </SideNav>
  
  
  <Content>
      <!-- <Grid>
          <Row>
              <Column>
                  Content
              </Column>
          </Row>
      </Grid> -->
      <slot />
  </Content>
  