# Application Layout

* [Design Guidelines](/documentation/app-layout#top)
* [Code & Examples](/documentation/app-layout#examples)

##### A properly structured layout enforces an optimal, consistent experience across applications.

### Layout

**.main-container:**

The `.main-container` is a vertical flexbox which wraps the following components:

* [App-Level Alert](/documentation/alerts)
* [Header](/documentation/header)
* [Subnav](/documentation/header)
* Content Container

**Note:** Although Clarity does not have a footer component, a custom footer can be added in the main-container.

**.content-container:**

The `.content-container` is a horizontal flexbox which wraps the following components:

* Content Area
* [Sidenav](/documentation/sidenav)

App Level Alert

Action

[Project Clarity](#)

* [Subnav Link 1](javascript://)
* [Subnav Link 2](javascript://)
* [Subnav Link 3](javascript://)
* [Subnav Link 4](javascript://)
* [Subnav Link 5](javascript://)

Content Area

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque eu odio nisi. Vestibulum dignissim eget massa sit amet feugiat. Quisque auctor mattis quam eu suscipit. Morbi ipsum risus, feugiat vitae sem at, tincidunt elementum magna. Phasellus tristique posuere dui, ut tempus felis sagittis quis. Integer iaculis ultrices elit, sed venenatis eros. Vivamus interdum semper velit eget gravida. Sed finibus eget lacus sed semper. Suspendisse fringilla, tellus in molestie cursus, sapien purus volutpat lacus, eget venenatis erat est vitae libero. Aliquam et orci hendrerit, consequat purus non, imperdiet ipsum.

Sidenav

* Link 1
* Link 2
* Link 3
* Link 4
* Link 5
* Link 6

```html
<div class="main-container">
    <div class="alert alert-app-level">
        ...
    </div>
    <header class="header header-6">
        ...
    </header>
    <nav class="subnav">
        ...
    </nav>
    <div class="content-container">
        <div class="content-area">
            ...
        </div>
        <nav class="sidenav">
            ...
        </nav>
    </div>
</div>
```

### Basic Structure

Two constants of an app built in Clarity are the header and content area. These are the blocks upon which you build your app model.

![Header and Content Area](assets/images/documentation/app-layout/header_contentarea.png?1481674789140619000)

##### Header

The [header](/documentation/header) is for branding and app-level elements such as navigation, search, and account settings.

##### Content Area

The content area is where users focus their attention most of the time, gathering information and performing tasks–it is the canvas for your application. As the largest portion of your app, the content area is always visible.

### Layout

Your layout should reflect the information or workflow of the selected [navigation](/documentation/navigation). When laying out the content, keep the following in mind:

* The flow of content–how to create a hierarchy and layout that draws attention to the areas of importance
* The importance of designing to the [grid](/documentation/grid)
* How to aid users in completing their tasks
* How to handle large amounts of data
* Responsive design (if that is part of your product’s goals)

##### Common Layout Patterns

Content can consist of any of the [Clarity components](/documentation), or no components and just information. Following are common layout patterns and recommended usage. For information on navigation components, header, subnav, and sidenav, see [Navigation](/documentation/navigation).

###### Cards

![Cards](assets/images/documentation/app-layout/cards.png?1481674789140619000)

[Cards](/documentation/cards) are for presenting high-level information and guiding users to related actions and details. Cards might include a combination of text, images, and data visualizations.

Benefits of using cards include:

* Ability to see data in a collection
* Facilitates scanning of information
* Works well across platforms

###### Tables and Datagrids

![Tables and Datagrids](assets/images/documentation/app-layout/tables.png?1481674789140619000)

[Tables](/documentation/tables) and datagrids are for good for managing large amounts of data. These layouts work well when users need to compare data and perform batch operations.

A table is a static view. A datagrid provides users flexibility in viewing the data, including filtering and sorting.

Complex tables and datagrids work best on larger screens.

###### Forms

![Forms](assets/images/documentation/app-layout/forms.png?1481674789140619000)

[Forms](/documentation/forms) are for collecting data from users. Forms are comprised of other components, including labels, input fields, labels, checkboxes, radio buttons, and text.

A benefit of a form is that users can see what information they must provide. Conversely, too many fields can discourage the user.

Inline forms are better than modals in cases where you don't want to block users from performing other actions.

###### Tabs

![Tabs](assets/images/documentation/app-layout/tabs.png?1481674789140619000)

[Tabs](/documentation/tabs) appear in a single, non-scrollable row, at the top of the content area. They are good for breaking content into separate, related views.

Tabs are not appropriate if users need to compare data across views.

###### White Space and Typography

![White Space and Typography](assets/images/documentation/app-layout/typography.png?1481674789140619000)

White space and [typography](/documentation/typography) are important elements in conveying hierarchy. These elements direct users to what they should view next and make the content and data easier to parse. They also helps bring consistency to an app.

###### Button Placement

In the content area, buttons are left-aligned, with the primary button in the leftmost position. This placement supports the F-pattern layout.

![Buttons align left in content area](assets/images/documentation/app-layout/do_button_alignment.png?1481674789140619000)

**Do.** Left-alignment puts buttons closest to the content.

![Buttons do not align right in content area](assets/images/documentation/app-layout/dont_button_alignment.png?1481674789140619000)

**Don't.**On the right, buttons might appear separate from content.

#### Using Vertical Rhythm for Layout

Vertical rhythm is the repetition of spatial relationships in a design. A consistent rhythm gives elements a uniform and balanced placement in a design. The more consistent the design, the easier it is for users to read and understand.

###### The Clarity Baseline is 24px

All elements in Clarity are _designed_ with a 24px baseline:

* The visual height of all components and text elements is in multiples of 24px.
* The vertical white space between elements is also in multiples of 24px.

![24px Baseline](assets/images/documentation/app-layout/24_baseline.png?1481674789140619000)

###### Repeat 24px in Your Layout

Design the vertical margins and padding between elements using the Clarity baseline. A multiple of 24px can be a whole or half-ratio. Common numbers include: 6px, 12px, 18px, 24px, 30px, 36px, 42px, 48px, 54px, 60px, 66px, 72px.

### Code & Examples

Clarity layouts and components are _designed_ with a "24px baseline". This means that the visual size of our components is expressed in clean multiples of 24.

But starting with version 3.0, the Clarity CSS _code's_ rem values are derived from a root font-size of 20px!

Why the difference?

#### Rem Sizing

In its underlying code, the Clarity styles had to move away from a root font-size of 24px for a couple of reasons:

* 24px was not a clean multiple of many common sizes. 1px, for example, had to be derived from 0.04166667rem. 16px, likewise, had a measurement of 0.6666667rem. The lack of clean multiples left us at the mercy of browsers rounding out our values. This introduced inconsistency across browsers and sloppy line rendering in many cases.
* Early styling decisions before Clarity 1.0 broke expected browser sizing preferences and negatively impacted the accessibility of Clarity for some users.

The changes to "rem" sizing in Clarity addresses both of those concerns. But there are a few caveats to keep in mind.

##### Design remains at 24px, underlying code is at 20px

The visual baseline for our design system remains 24px with a base grid of 6px. _For designers using the Clarity Design System, nothing has changed_.

Developers, however, must convert 24px based designs to a system that uses 20px at its core.

##### Converting from old 24px-based styles to new 20px based styles

First and most importantly, you do not need to do _anything_ if your application does not use rem values or percentages that rely on Clarity's default root font-size.

If you do, however, rely on the rem sizing available in Clarity, there are a number of options available to update the old code to the new rem sizing.

###### Set hard pixel values (Not recommended)

If you are already setting hard pixel values outside of Clarity, no change is needed on your part. Setting hard pixel values is not recommended, however, because it breaks accessibility and browser text resizing features.

###### Update your rem values

If you are using rem values outside of Clarity, you can update them by either:

* multiplying them by 1.2 – so a value of `1.4rem` in a SASS file becomes `1.2 * 1.4rem`
* doing the math upfront and updating rem values in place – so that `1.4rem` becomes `1.68rem`

###### Use Clarity's $clrBaselineRem\_\* variables (Recommended)

[Clarity has a number of size variables that you can use in your applications](//github.com/vmware/clarity/blob/master/src/clr-core/styles/variables/_variables.global.scss). It is recommended that you update your application to make use of them. This is the safest course of action going forward and will result in the least amount of rework in the future.

###### What if I can't do this right now?

If you would prefer to update Clarity to version 3.x and cannot update the sizes in your application that rely on Clarity's baseline, you can override the `$clr-baseline-denominator` SASS variable. Setting it to `24` ignores the baseline changes, putting everything back to the pre-3.0 24px baseline.

Clarity implemented this workaround to make the transition to 3.0 easier on our users, allowing them to take on the work of updating their rem sizes at their own pace if they need to. Note that this should be consider a temporary workaround, however, not a long-term solution. There is no guarantee that this override will be supported beyond 3.0.

#### Customizing the root font-size

Clarity uses [rem units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Values_and_units) for its whitespace and sizing. If the 24px vertical baseline is too large or too small for your needs, you can edit this globally across a Clarity application by changing the `font-size` style of the `html` element, as in the example below.

```html
html {
    /*
     * the following line of CSS would change pre-3.0 Clarity to a 20px vertical rhythm with a
     * 5px grid in 2.0 and * earlier
     */
    font-size: 20px;

    /* for 3.0 and later versions, divide the preferred root value by 1.2 to get a pixel
     * equivalency
     */
    font-size: calc(20px/1.2);

    /* ...or do the math yourself so you don't need calc()! */
    font-size: 16.666667px;

    /*
     * It's recommended, however, that percentage units be used to allow for accessible browser text
     * resizing.  Given that our current 24px baseline lives on top of a 20px (125%) root font size, we
     * would need to divide our preferred baseline by 0.192 to get the percentage we need.
     *
     * So the following percentage would produce a UI that follows a design with a 20px vertical rhythm
     * and 5px grid – 20 ÷ 0.192 = 104.166667.
     */
    font-size: 104.1667%;

    /*
     * The following percentage would produce a UI that follows a design with a 28px vertical rhythm
     * and 7px grid.
     * 28 ÷ 0.192 = 145.83333
     */
    font-size: 145.83333%;

    /*
     * The following percentage would produce a UI that follows a design with a 32px vertical rhythm
     * and 8px grid – 32 ÷ 0.192 = 166.66667.
     */
    font-size: 166.66667%;
}
```

Note that the declaration on the `html` selector needs to happen _after_ the Clarity CSS has been loaded. Also note that the "grid" for Clarity layouts and components is equal to one-fourth of the baseline. So instead of a 6px grid, the example above will put your application on a 5px grid.