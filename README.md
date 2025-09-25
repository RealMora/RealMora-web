import React from "react";

// RealMora Web - Single-file Next.js/React landing page template
// - Tailwind CSS utility classes used (no imports here)
// - Uses shadcn/ui-like components (assumed available in your project)
// - Replace placeholders and wiring with real APIs (Auth, Payments, Discord, Forum)

export default function RealMoraLanding() {
  return (
    <div className="min-h-screen bg-gradient-to-b from-gray-900 via-slate-900 to-black text-slate-100">
      {/* Top Nav */}
      <header className="backdrop-blur-sm sticky top-0 z-40 border-b border-slate-800">
        <div className="max-w-7xl mx-auto px-6 py-4 flex items-center justify-between gap-6">
          <div className="flex items-center gap-3">
            <div className="w-12 h-12 rounded-2xl bg-gradient-to-br from-amber-500 to-rose-600 flex items-center justify-center shadow-lg">
              <span className="font-bold text-black">RM</span>
            </div>
            <div>
              <h1 className="text-lg font-extrabold tracking-tight">RealMora Web</h1>
              <p className="text-xs text-slate-400">Minecraft • Roblox • Community</p>
            </div>
          </div>

          <nav className="flex items-center gap-4">
            <a className="text-sm hover:underline" href="#news">Novosti</a>
            <a className="text-sm hover:underline" href="#shop">Prodavnica</a>
            <a className="text-sm hover:underline" href="#forum">Forum</a>
            <a className="text-sm hover:underline" href="#partners">Partneri</a>
            <div className="hidden md:block">
              <button className="px-3 py-1 rounded-md bg-emerald-500 text-black font-semibold">Prijavi se</button>
            </div>
            <LanguageSwitcher />
          </nav>
        </div>
      </header>

      {/* Hero */}
      <main className="max-w-7xl mx-auto px-6 py-12">
        <section className="grid grid-cols-1 md:grid-cols-2 gap-8 items-center">
          <div>
            <h2 className="text-4xl md:text-5xl font-extrabold leading-tight">Dobrodošao u <span className="text-amber-400">RealMora</span></h2>
            <p className="mt-4 text-slate-300 max-w-xl">Zajednica posvećena Minecraft i Roblox projektima — serveri, event-ovi, VIP paketi i mesto gde igrači rastu. Upravljaj svojom zajednicom, kupuj premium pakete i poveži Discord direktno sa sajtom.</p>

            <div className="mt-6 flex gap-3">
              <a href="#shop" className="inline-flex items-center gap-2 px-4 py-2 rounded-lg bg-amber-500 text-black font-semibold">Kupi VIP</a>
              <a href="#news" className="inline-flex items-center gap-2 px-4 py-2 rounded-lg border border-slate-700">Saznaj više</a>
            </div>

            <div className="mt-8 grid grid-cols-2 gap-3 max-w-md">
              <Stat label="Igrača online" value="123" />
              <Stat label="Aktivnih događaja" value="4" />
              <Stat label="VIP prodaja" value="742" />
              <Stat label="Partnera" value="8" />
            </div>
          </div>

          <div className="relative">
            {/* Illustration / Avatar placeholder */}
            <div className="mx-auto w-full max-w-md rounded-2xl bg-gradient-to-br from-slate-800 to-slate-700 p-6 shadow-2xl">
              <div className="flex items-center gap-4">
                <div className="w-20 h-20 rounded-full bg-white/5 flex items-center justify-center text-2xl font-bold">You</div>
                <div>
                  <div className="text-sm text-slate-300">Ćelav, bela košulja</div>
                  <div className="mt-1 text-lg font-bold">Tvoj Nick</div>
                </div>
              </div>

              <div className="mt-6">
                <div className="w-full h-48 bg-[url('/placeholder-mc.png')] bg-cover rounded-lg border border-slate-700/50 flex items-end p-4">
                  <div className="bg-black/60 p-3 rounded-md">
                    <div className="text-xs text-slate-200">Mining mode</div>
                    <div className="text-sm font-semibold">Kopaš rude na dnu pećine</div>
                  </div>
                </div>
              </div>

            </div>
          </div>
        </section>

        {/* Features */}
        <section className="mt-12 grid grid-cols-1 md:grid-cols-3 gap-6">
          <Feature title="Shop & VIP" description="Prodaj VIP pakete za Minecraft i Roblox. Integracija plaćanja karticom i PayPal-om." />
          <Feature title="Forum & Obaveštenja" description="Forum za igrače, najave i sekcije za ideje i support." />
          <Feature title="Discord & Integracija" description="Poveži Discord - prikaz online članova i automatske role po VIP kupovini." />
        </section>

        {/* News */}
        <section id="news" className="mt-12">
          <div className="flex items-center justify-between">
            <h3 className="text-2xl font-bold">Najnovije vesti</h3>
            <a href="#news" className="text-sm text-slate-400">Pregledaj sve</a>
          </div>

          <div className="mt-4 grid grid-cols-1 md:grid-cols-3 gap-4">
            {sampleNews.map((n) => (
              <article key={n.id} className="p-4 bg-slate-800/50 rounded-lg border border-slate-700">
                <h4 className="font-semibold">{n.title}</h4>
                <p className="mt-2 text-sm text-slate-300">{n.excerpt}</p>
                <div className="mt-3 flex items-center justify-between text-xs text-slate-400">
                  <span>{n.date}</span>
                  <a className="underline" href="#">Čitaj</a>
                </div>
              </article>
            ))}
          </div>
        </section>

        {/* Shop preview */}
        <section id="shop" className="mt-12">
          <h3 className="text-2xl font-bold">Prodavnica</h3>
          <p className="text-slate-400 mt-2">Brzo i sigurno plaćanje karticom (Stripe) ili PayPal. Nakon kupovine automatska aktivacija VIP-a na serveru.</p>

          <div className="mt-6 grid grid-cols-1 md:grid-cols-3 gap-4">
            {sampleProducts.map((p) => (
              <div key={p.id} className="p-4 rounded-lg bg-gradient-to-br from-slate-800/40 to-slate-700 border border-slate-700">
                <div className="flex items-center justify-between">
                  <div>
                    <div className="text-sm text-slate-300">{p.category}</div>
                    <div className="text-lg font-semibold">{p.title}</div>
                  </div>
                  <div className="text-2xl font-bold">{p.price}</div>
                </div>
                <div className="mt-4 flex gap-2">
                  <button className="flex-1 py-2 rounded-md border border-slate-600">Detalji</button>
                  <button className="py-2 px-4 rounded-md bg-amber-500 text-black font-semibold">Kupi</button>
                </div>
              </div>
            ))}
          </div>
        </section>

        {/* Forum preview */}
        <section id="forum" className="mt-12">
          <div className="flex items-center justify-between">
            <h3 className="text-2xl font-bold">Forum</h3>
            <a href="#forum" className="text-sm text-slate-400">Idi na forum</a>
          </div>

          <div className="mt-4 grid grid-cols-1 md:grid-cols-2 gap-4">
            <div className="p-4 rounded-lg bg-slate-800/50 border border-slate-700">
              <h4 className="font-semibold">General</h4>
              <p className="text-sm text-slate-300 mt-2">Diskusije o serveru, prijedlozi i novaci.</p>
            </div>
            <div className="p-4 rounded-lg bg-slate-800/50 border border-slate-700">
              <h4 className="font-semibold">Support</h4>
              <p className="text-sm text-slate-300 mt-2">Tehnička pomoć i prijave bagova.</p>
            </div>
          </div>
        </section>

        {/* Discord & Partners */}
        <section id="partners" className="mt-12 grid md:grid-cols-2 gap-6">
          <div className="p-6 rounded-lg bg-slate-800/40 border border-slate-700">
            <h3 className="text-xl font-bold">Discord integracija</h3>
            <p className="text-slate-300 mt-2">Prikaži ko je online, pozovi igrače i poveži uloge sa kupovinama. (Potreban bot i Discord OAuth)</p>
            <div className="mt-4">
              <button className="px-4 py-2 rounded-md bg-indigo-600 font-semibold">Poveži Discord</button>
            </div>
          </div>

          <div className="p-6 rounded-lg bg-slate-800/40 border border-slate-700">
            <h3 className="text-xl font-bold">Partnerstva</h3>
            <p className="text-slate-300 mt-2">Prikaži partnere i omogući prijavu za partnerstvo. Automatsko isticanje partner logotipa.</p>
            <div className="mt-4 grid grid-cols-3 gap-3 items-center">
              <div className="h-12 bg-white/5 rounded flex items-center justify-center">P1</div>
              <div className="h-12 bg-white/5 rounded flex items-center justify-center">P2</div>
              <div className="h-12 bg-white/5 rounded flex items-center justify-center">P3</div>
            </div>
          </div>
        </section>

        {/* Footer */}
        <footer className="mt-12 py-8 text-slate-500 border-t border-slate-800">
          <div className="max-w-7xl mx-auto px-6 flex flex-col md:flex-row items-center justify-between gap-4">
            <div>
              <div className="font-semibold">RealMora Web</div>
              <div className="text-sm">© {new Date().getFullYear()} RealMora. Sva prava zadržana.</div>
            </div>
            <div className="flex gap-4 items-center">
              <a className="text-sm hover:underline" href="#">Privatnost</a>
              <a className="text-sm hover:underline" href="#">Uslovi</a>
              <a className="text-sm hover:underline" href="#">Kontakt</a>
            </div>
          </div>
        </footer>
      </main>
    </div>
  );
}


/* ------------------------ Small components & sample data ------------------------ */

function Stat({ label, value }) {
  return (
    <div className="p-3 bg-slate-800/30 rounded-lg border border-slate-700">
      <div className="text-xs text-slate-400">{label}</div>
      <div className="text-xl font-bold mt-1">{value}</div>
    </div>
  );
}

function Feature({ title, description }) {
  return (
    <div className="p-6 rounded-xl bg-gradient-to-br from-slate-800/40 to-slate-700 border border-slate-700">
      <h4 className="font-semibold text-lg">{title}</h4>
      <p className="mt-2 text-slate-300 text-sm">{description}</p>
      <div className="mt-4">
        <a className="text-sm underline" href="#">Saznaj više</a>
      </div>
    </div>
  );
}

function LanguageSwitcher() {
  return (
    <div className="inline-flex items-center rounded-md border border-slate-700 overflow-hidden">
      <button className="px-3 py-1 text-sm">SR</button>
      <button className="px-3 py-1 text-sm text-slate-400">EN</button>
    </div>
  );
}

const sampleNews = [
  { id: 1, title: "Veliki update na Minecraft serveru", excerpt: "Dodali smo nove minigame-ove, spawn i nagrade.", date: "3h" },
  { id: 2, title: "Roblox event — Vikend turnir", excerpt: "Prijavi se i osvoji VIP paket.", date: "1d" },
  { id: 3, title: "Partner program otvoren", excerpt: "Prijavi se za partnerstvo i promovisi svoj server.", date: "3d" },
];

const sampleProducts = [
  { id: 1, category: "Minecraft VIP", title: "Gold VIP - 30 dana", price: "€4.99" },
  { id: 2, category: "Roblox VIP", title: "Diamond VIP - trajno", price: "€9.99" },
  { id: 3, category: "Bundle", title: "Starter Pack + VIP", price: "€12.99" },
];

/*
  NEXT STEPS & INTEGRATION NOTES (copy to project README):
  - Add authentication (NextAuth.js) for Discord/Google/email logins.
  - Implement backend endpoints for products, checkout, and webhooks (Stripe/PayPal).
  - Create a secure admin panel (role-based) to post news, manage products and forum moderation.
  - For forum consider embedding Discourse or using a headless forum (e.g. NodeBB, Flarum) and styling to match.
  - Discord: register OAuth app + bot for role assignment and status widget.
  - Internationalization: use next-i18next or built-in Next.js i18n routing for translations.

  When ready, daj mi pristup repozitorijumu ili reci da napravim i backend template (Node/Django) pa povežemo checkout i baze.
*/
