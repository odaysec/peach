<script setup lang="ts">
import { reportError } from "~/utils/report-error";

type MonitorScreen =
  | "welcome"
  | "cs2"
  | "hackclub"
  | "coinbase"
  | "sourcegraph"
  | "github"
  | "summer"
  | "hackatime"
  | "email"
  | "signal"
  | "telegram"
  | "markets";

const activeScreen = ref<MonitorScreen>("welcome");
const projectsOpen = ref(false);

const set = (s: MonitorScreen = "welcome") => (activeScreen.value = s);

const linkMonitor = (s: MonitorScreen) => {
  const on = () => set(s);
  const off = () => set();
  return { mouseenter: on, focus: on, touchstart: on, mouseleave: off, blur: off };
};
</script>

<template>
  <NuxtErrorBoundary @error="(e) => reportError('home:background', e)">
    <Background />
  </NuxtErrorBoundary>

  <main class="min-h-screen px-6 py-12 sm:px-8 lg:px-12">
    <div class="mx-auto flex min-h-[calc(100vh-6rem)] max-w-6xl items-center">
      <div class="grid w-full gap-10 lg:grid-cols-[minmax(0,40rem)_minmax(18rem,25rem)] lg:gap-14">
        <div class="flex flex-col justify-center">
          <h3 class="text-3xl text-white sm:text-4xl">hi, i'm number7 (aka Thomas Andri Hutomo)</h3>

          <p class="mt-8 max-w-lg text-lg leading-8 text-white/82">
            As a Cyber Security Intelligence Professional, I design and develop innovative security tools to strengthen the resilience of Indonesia's national technology systems. This role involves research and development of cyber defense solutions to protect the country's digital infrastructure and sensitive information, supporting Indonesia's vision of a secure and sovereign digital ecosystem.
            <a
              href="https://hub.opzero.id/"
              class="text-blue-400 underline"
              v-on="linkMonitor('markets')"
              >Research Hub</a
            >, play
            <a
              href="https://github.com/odaysec/"
              class="text-blue-400 underline"
              v-on="linkMonitor('cs2')"
              >Github</a
            >, and build fun projects.
          </p>

          <div class="mt-6 flex flex-col gap-3">
            <Disclosure label="work">
              <p class="text-lg leading-8 text-white/82">
                i am currently a full-time work on Deputi VI also i have done as global contribute work with
                <a
                  href="https://github.com/vercel/turborepo"
                  class="text-blue-400 underline"
                  v-on="linkMonitor('vercel')"
                  >Vercel Company</a
                >,
                <a
                  href="https://soc.jakarta.go.id//certificate/view?token=$2y$13$qAdCfcD9FX4p9AEUxawhpO3NGNVfz7m5pDdBFYyOyGmkKRpoa8nxO"
                  class="text-blue-400 underline"
                  v-on="linkMonitor('DKI Jakarta')"
                  >SOC DKI Jakarta</a
                >,
                <a
                  href="https://bughunters.google.com/profile/702cda82-b10f-4d6c-b509-65434bd89b15/awards"
                  class="text-blue-400 underline"
                  v-on="linkMonitor('Google')"
                  >Google VRP</a
                >,
                <a
                  href="https://esign.dpr.go.id/file/file/storage/"
                  class="text-blue-400 underline"
                  v-on="linkMonitor('DPR')"
                  >Pusat Teknologi Informasi Sekretariat Jenderal DPR RI</a
                >,
                <a
                  href="https://github.com/advisories?query=credit%3Aodaysec"
                  class="text-blue-400 underline"
                  v-on="linkMonitor('GitHub')"
                  >GitHub Advisory Team</a
                >, global governments, and others in the past.
              </p>
            </Disclosure>

            <Disclosure label="projects" action @activate="projectsOpen = true" />

            <Disclosure label="contact">
              <p class="text-lg leading-8 text-white/82">
                you can reach me via
                <a
                  href="mailto:hello@3kh0.net"
                  class="text-blue-400 underline"
                  v-on="linkMonitor('email')"
                  >email</a
                >,
                <a
                  href="https://signal.me/#eu/EnC26yk3rkDfP2JPoguBZYjCVhMD6_xAGxu1L4UzhdK0bnQgDHdIQLCQjR6eBdZF"
                  class="text-blue-400 underline"
                  v-on="linkMonitor('signal')"
                  >signal</a
                >
                or
                <a
                  href="https://t.me/doober"
                  class="text-blue-400 underline"
                  v-on="linkMonitor('telegram')"
                  >telegram</a
                >.
              </p>
            </Disclosure>

            <Disclosure label="links">
              <p class="mb-2 text-lg leading-8 text-white/82">
                you can find me on other platforms as well:
                <a href="https://github.com/3kh0" class="text-blue-400 underline" target="_blank"
                  >github</a
                >,
                <a
                  href="https://old.reddit.com/u/3kh0_reddit/"
                  class="text-blue-400 underline"
                  target="_blank"
                  >reddit</a
                >, and
                <a
                  href="https://www.youtube.com/@3kh0"
                  class="text-blue-400 underline"
                  target="_blank"
                  >youtube</a
                >. while you are here, enjoy this collection of fun 88x31 buttons!
              </p>
              <div class="mb-2 flex flex-wrap gap-2">
                <img
                  src="/88x31/mlm.png"
                  srcset="/88x31/mlm.png 1x, /88x31/mlm@2x.png 2x"
                  width="88"
                  height="31"
                  alt="MLM 88x31 button"
                  class="transition-transform duration-200 hover:scale-110"
                />
                <a href="https://developer.valvesoftware.com/wiki/Source" target="_blank">
                  <img
                    src="/88x31/source.png"
                    srcset="/88x31/source.png 1x, /88x31/source@2x.png 2x"
                    width="88"
                    height="31"
                    alt="Source Engine 88x31 button"
                    class="transition-transform duration-200 hover:scale-110"
                  />
                </a>
                <a href="https://github.com/gorhill/uBlock" target="_blank">
                  <img
                    src="/88x31/ublock.png"
                    srcset="/88x31/ublock.png 1x, /88x31/ublock@2x.png 2x"
                    width="88"
                    height="31"
                    alt="uBlock Origin 88x31 button"
                    class="transition-transform duration-200 hover:scale-110"
                  />
                </a>
                <a href="https://www.getmonero.org/" target="_blank">
                  <img
                    src="/88x31/xmr.png"
                    srcset="/88x31/xmr.png 1x, /88x31/xmr@2x.png 2x"
                    width="88"
                    height="31"
                    alt="Monero 88x31 button"
                    class="transition-transform duration-200 hover:scale-110"
                  />
                </a>
              </div>
              <p class="mb-2 text-lg leading-8 text-white/82">and of course, a few friends:</p>
              <div class="mb-2 flex flex-wrap gap-2">
                <a href="https://sundial.city/" target="_blank">
                  <img
                    src="/88x31/sundial.gif"
                    srcset="/88x31/sundial.gif 1x, /88x31/sundial@2x.gif 2x"
                    width="88"
                    height="31"
                    alt="sundial.city 88x31 button"
                    class="transition-transform duration-200 hover:scale-110"
                  />
                </a>
                <a href="https://aconlin.com/" target="_blank">
                  <img
                    src="/88x31/acon.gif"
                    srcset="/88x31/acon.gif 1x, /88x31/acon@2x.gif 2x"
                    width="88"
                    height="31"
                    alt="aconlin.com 88x31 button"
                    class="transition-transform duration-200 hover:scale-110"
                  />
                </a>
                <a href="https://bomberfish.ca/" target="_blank">
                  <img
                    src="/88x31/bomberfish.png"
                    srcset="/88x31/bomberfish.png 1x, /88x31/bomberfish@2x.png 2x"
                    width="88"
                    height="31"
                    alt="bomberfish.ca 88x31 button"
                    class="transition-transform duration-200 hover:scale-110"
                  />
                </a>
                <a href="https://glutesha.me/" target="_blank">
                  <img
                    src="/88x31/glutesha.png"
                    srcset="/88x31/glutesha.png 1x, /88x31/glutesha@2x.png 2x"
                    width="88"
                    height="31"
                    alt="glutesha.me 88x31 button"
                    class="transition-transform duration-200 hover:scale-110"
                  />
                </a>
                <a href="https://prpl.wtf/" target="_blank">
                  <img
                    src="/88x31/prpl.gif"
                    srcset="/88x31/prpl.gif 1x, /88x31/prpl@2x.gif 2x"
                    width="88"
                    height="31"
                    alt="prpl.wtf 88x31 button"
                    class="transition-transform duration-200 hover:scale-110"
                  />
                </a>
                <a href="https://foxmoss.com/" target="_blank">
                  <img
                    src="/88x31/foxmoss.png"
                    srcset="/88x31/foxmoss.png 1x, /88x31/foxmoss@2x.png 2x"
                    width="88"
                    height="31"
                    alt="foxmoss.com 88x31 button"
                    class="transition-transform duration-200 hover:scale-110"
                  />
                </a>
              </div>
              <p class="mb-2 text-lg leading-8 text-white/82">
                if you want to add mine, see below!
              </p>
              <a href="/button.png" target="_blank">
                <img
                  src="/button.png"
                  srcset="/button.png 1x, /button@2x.png 2x"
                  width="88"
                  height="31"
                  alt="3kh0.net 88x31 button"
                  class="transition-transform duration-200 hover:scale-110"
                />
              </a>
            </Disclosure>
          </div>
        </div>

        <div
          class="flex items-center justify-center lg:sticky lg:top-12 lg:h-[calc(100dvh-6rem)] lg:self-start lg:justify-end"
        >
          <div class="flex w-full max-w-100 flex-col gap-4">
            <NuxtErrorBoundary @error="(e) => reportError('home:monitor', e)">
              <Monitor :screen="activeScreen" />
            </NuxtErrorBoundary>
            <NuxtErrorBoundary @error="(e) => reportError('home:music', e)">
              <MusicPlayer />
            </NuxtErrorBoundary>
          </div>
        </div>
      </div>
    </div>
  </main>

  <NuxtErrorBoundary @error="(e) => reportError('home:projects', e)">
    <ProjectsMonitor :open="projectsOpen" @close="projectsOpen = false" />
  </NuxtErrorBoundary>
</template>
