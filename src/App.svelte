<script>
    import HamburgerMenu    from  './components/HamburgerMenu.svelte';
    import NavMenuItems     from  './components/NavMenuItems.svelte';
    import NavItem          from  './components/NavItem.svelte';
    import Overlay          from  './components/Overlay.svelte';
    import SecondarySection from  './components/SecondarySection.svelte'

    let change;
    $:overlay = change;
    $:visible = change;

    const clientWidth = document.documentElement.clientWidth;

    const navItems = [
        {
            href: '#home',
            title: 'Home',
            in: {
                delay: 200,
                duration: 400,
                x: -clientWidth,
            },
            out: {
                delay: 500,
                duration: 300,
                x: -clientWidth,
            },
        },
        {
            href: '#about',
            title: 'About',
            in: {
                delay: 400,
                duration: 400,
                x: -clientWidth,
            },
            out: {
                delay: 400,
                duration: 300,
                x: -clientWidth,
            },
        },
        {
            href: '#skills',
            title: 'Skills',
            in: {
                delay: 600,
                duration: 400,
                x: -clientWidth,
            },
            out: {
                delay: 300,
                duration: 300,
                x: -clientWidth,
            },
        },
        {
            href: '#projects',
            title: 'Projects',
            in: {
                delay: 800,
                duration: 400,
                x: -clientWidth,
            },
            out: {
                delay: 200,
                duration: 300,
                x: -clientWidth,
            },
        },
        {
            href: '#contact',
            title: 'Contact',
            in: {
                delay: 1000,
                duration: 400,
                x: -clientWidth,
            },
            out: {
                delay: 100,
                duration: 300,
                x: -clientWidth,
            },
        },
    ];

    const secondarySections = [
        {
            id: 'about',
            title: 'Learn More About Me',
        },
        {
            id: 'skills',
            title: 'These Are My Strengths',
        },
        {
            id: 'projects',
            title: 'These Are My Results',
        },
        {
            id: 'contact',
            title: 'Available Anytime',
        },
    ];

    const toggleNav = () => change = !change;
</script>

<Overlay {overlay}>
    <NavMenuItems>
        {#each navItems as item}
            <NavItem
                {visible}
                href={item.href}
                title={item.title}
                flyIn={item.in}
                flyOut={item.out}
                on:click={toggleNav}
            />
        {/each}
    </NavMenuItems>
</Overlay>

<HamburgerMenu on:click={toggleNav} {change} />

<section id="home"><a href="/">Jason Kirklin</a></section>

{#each secondarySections as section}
    <SecondarySection sectionId={section.id} sectionTitle={section.title} />
{/each}