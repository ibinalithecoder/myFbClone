Facebook’s front page (or main feed layout) is built using a multi-column responsive layout, and yes — each column behaves like its own scrollable frame/container.
Here’s how it works in a simple explanation:

✅ How Facebook’s 3-Column Layout Works
1. The layout is divided into 3 major columns

Left Sidebar (Navigation, profile, menu)

Center Feed (Posts)

Right Sidebar (Contacts, groups, sponsored)

All three columns are placed inside a flexbox container (sometimes CSS Grid is used in parts).

✅ 2. Each column has its own scrollable container

Facebook does NOT scroll the entire page as one block.

Instead:

✔ The center feed scrolls normally
✔ The left and right columns stay fixed and scroll independently inside their own frames

This is achieved by:

.left-sidebar,
.right-sidebar {
    position: sticky;
    top: 0;
    height: 100vh; /* full screen height */
    overflow-y: auto; /* independent scroll */
}


This makes the sidebar stick in place while the inner content scrolls.

✅ 3. The center column scrolls with the page

The middle feed is the only part that scrolls with the entire page.

✅ 4. The layout uses something like this:
.container {
    display: flex;
}

.left-sidebar {
    width: 25%;
    position: sticky;
    top: 0;
    height: 100vh;
    overflow-y: auto;
}

.feed {
    width: 50%;
}

.right-sidebar {
    width: 25%;
    position: sticky;
    top: 0;
    height: 100vh;
    overflow-y: auto;
}

⭐ In simple words

Facebook uses 3 separate containers, and each one has its own scrollbar, but visually:

➝ You only see the main page scrolling
➝ Sidebars scroll inside themselves when needed

It feels natural and smooth.