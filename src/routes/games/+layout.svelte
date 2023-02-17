<script>
    import { page } from '$app/stores'
</script>

<section>
    <nav>
        <svg viewBox="0 0 2 3" aria-hidden="true">
			<path d="M0,0 L1,2 C1.5,3 1.5,3 2,3 L2,0 Z" />
		</svg>
        <ul>
            <!-- <li aria-current={$page.url.pathname === '/games' ? 'page' : undefined}>
                <a href='/games'>games</a>
            </li> -->
            <li aria-current={$page.url.pathname.startsWith('/games/sverdle') ? 'page' : undefined}>
                <a href='/games/sverdle'>sverdle</a>
            </li>
        </ul>
        <svg viewBox="0 0 2 3" aria-hidden="true">
			<path d="M0,0 L0,3 C0.5,3 0.5,3 1,2 L2,0 Z" />
		</svg>
    </nav>
    <main>Games</main>
    <aside>
        <slot />
    </aside>
</section>

<style>
    section {
        display: grid;
        grid-template-columns: repeat(2, auto);
        grid-template-rows:  repeat(2, auto);
    }

    section nav {
        grid-area: 1/1/2/3;
        text-align: center;
    }

    nav {
		display: flex;
		justify-content: center;
		--background: rgba(255, 255, 255, 0.7);
	}

	svg {
		height: 1.75em;
		display: block;
	}

	path {
		fill: var(--background);
	}

	ul {
		position: relative;
		padding: 0;
		margin: 0;
		height: 1.75em;
		display: flex;
		justify-content: center;
		align-items: center;
		list-style: none;
		background: var(--background);
		background-size: contain;
	}

	li {
		position: relative;
		height: 100%;
	}

	li[aria-current='page']::before {
		--size: 6px;
		content: '';
		width: 0;
		height: 0;
		position: absolute;
		top: 0;
		left: calc(50% - var(--size));
		border: var(--size) solid transparent;
		border-top: var(--size) solid var(--color-theme-1);
	}

	nav a {
		display: flex;
		height: 100%;
		align-items: center;
		padding: 0 0.5rem;
		color: var(--color-text);
		font-weight: 700;
		font-size: 0.8rem;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		text-decoration: none;
		transition: color 0.2s linear;
	}

	a:hover {
		color: var(--color-theme-1);
	}
</style>