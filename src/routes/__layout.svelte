<script>
  import '$lib/styles/normalise.css';
  import '$lib/styles/index.scss';

  import '@fontsource/merriweather/400.css';
  import '@fontsource/merriweather/700.css';
  import '@fontsource/fira-sans/400.css';

  import { COPYRIGHT_ENTITY } from '$lib/constants/entities';
  import ExternalLink from '$lib/components/ExternalLink.svelte';
  import FacebookIcon from '$lib/components/Icons/Facebook.svelte';
  import GitHubIcon from '$lib/components/Icons/GitHub.svelte';
  import LinkedinIcon from '$lib/components/Icons/LinkedIn.svelte';
  import KevinMacKenzieCredit from '$lib/components/KevinMacKenzieCredit.svelte';
  import TiktokIcon from '$lib/components/Icons/Tiktok.svelte';
  import TwitterIcon from '$lib/components/Icons/Twitter.svelte';
  import website from '$lib/config/website';

  const { facebookPage, githubPage, linkedinProfile, tiktokUsername, twitterUsername } = website;
</script>

<main>
  <slot />
</main>
<footer class="footer-container">
  <div>
    Forked by <a
      aria-label="Open the Kevin MacKenzie site"
      href="https://thekevinmackenzie.com/"
      target="_blank"
      rel="noopener noreferrer">Kevin MacKenzie</a
    >. Copyright {COPYRIGHT_ENTITY} 2022.
  </div>
  <nav class="footer-icons">
    <ul>
      <li class="hover-jump">
        <ExternalLink
          ariaLabel="Go to the Kevin MacKenzie Tik Tok Page"
          href={`https://www.tiktok.com/${tiktokUsername}`}><TiktokIcon /></ExternalLink
        >
      </li>
      <li class="hover-jump">
        <ExternalLink ariaLabel="Go to the Kevin MacKenzie Facebook Page" href={facebookPage}
          ><FacebookIcon /></ExternalLink
        >
      </li>
      <li class="hover-jump">
        <ExternalLink
          ariaLabel="Go to the Kevin MacKenzie Twitter Page"
          href={`https://twitter.com/intent/user?screen_name=${twitterUsername}`}
          ><TwitterIcon /></ExternalLink
        >
      </li>
      <li class="hover-jump">
        <ExternalLink
          ariaLabel="Go to the Kevin MacKenzie Linked In Page"
          href={`https://uk.linkedin.com/in/${linkedinProfile}`}><LinkedinIcon /></ExternalLink
        >
      </li>
      <li class="hover-jump">
        <ExternalLink
          ariaLabel="Go to the Kevin MacKenzie Git Hub In Page"
          href={`https://github.com/${githubPage}`}><GitHubIcon /></ExternalLink
        >
      </li>
    </ul>
  </nav>
  <KevinMacKenzieCredit />
</footer>

<style lang="scss">
  .footer-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    max-width: $max-width-wrapper;
    margin: $spacing-12 auto $spacing-0;
    width: 100%;
  }

  .footer-icons {
    display: flex;
    list-style-type: none;

    ul {
      display: flex;
      margin: $spacing-6 $spacing-0;

      li {
        display: flex;
        margin: $spacing-0 $spacing-4 $spacing-0 $spacing-0;
      }
    }
  }

  @media (prefers-reduced-motion: no-preference) {
    .hover-jump {
      transition: all 0.25s ease-in-out;
    }
  }

  .hover-jump:focus,
  .hover-jump:hover {
    transform: translateY(-$spacing-2);
  }
</style>
