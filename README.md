import React, { useState } from "react";

// 67 Futsal Academy — Single-file site you can publish as-is
// How to use:
// 1) Edit text, links, and images below.
// 2) Export this component inside a React app (Vite/Next.js) or paste into a new project.
// 3) For a zero-config deploy, create a new Vite React app, drop this in src/App.jsx, run `npm run build`, then deploy to Netlify/Vercel.

export default function App() {
  const [open, setOpen] = useState(false);

  const navItems = [
    { href: "#home", label: "Home" },
    { href: "#about", label: "About" },
    { href: "#programs", label: "Programs" },
    { href: "#league", label: "Christmas League" },
    { href: "#schedule", label: "Schedule" },
    { href: "#contact", label: "Contact" },
  ];

  return (
    <div className="min-h-screen bg-neutral-50 text-neutral-900">
      {/* Top Bar */}
      <header className="sticky top-0 z-50 bg-white/80 backdrop-blur border-b border-neutral-200">
        <div className="max-w-7xl mx-auto px-4 py-3 flex items-center justify-between">
          <div className="flex items-center gap-3">
            <div className="w-10 h-10 rounded-2xl bg-orange-500 grid place-items-center shadow-sm">
              <span className="text-white font-black">67</span>
            </div>
            <div className="leading-tight">
              <div className="font-extrabold tracking-tight">67 Futsal Academy</div>
              <div className="text-xs text-neutral-500">Chesterfield, Missouri</div>
            </div>
          </div>

          {/* Desktop Nav */}
          <nav className="hidden md:flex items-center gap-6 text-sm">
            {navItems.map((item) => (
              <a key={item.href} href={item.href} className="hover:text-orange-600 transition-colors">
                {item.label}
              </a>
            ))}
            <a
              href="#register"
              className="rounded-2xl px-4 py-2 bg-orange-600 text-white font-semibold shadow hover:bg-orange-700"
            >
              Register
            </a>
          </nav>

          {/* Mobile menu button */}
          <button
            onClick={() => setOpen((v) => !v)}
            className="md:hidden inline-flex items-center justify-center w-10 h-10 rounded-xl border border-neutral-200"
            aria-label="Toggle menu"
          >
            <svg viewBox="0 0 24 24" className="w-6 h-6" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round">
              <path d="M4 6h16M4 12h16M4 18h16" />
            </svg>
          </button>
        </div>
        {open && (
          <div className="md:hidden border-t border-neutral-200">
            <div className="px-4 py-3 grid gap-2">
              {navItems.map((item) => (
                <a
                  key={item.href}
                  href={item.href}
                  onClick={() => setOpen(false)}
                  className="py-2"
                >
                  {item.label}
                </a>
              ))}
              <a
                href="#register"
                onClick={() => setOpen(false)}
                className="rounded-xl px-4 py-2 bg-orange-600 text-white font-semibold shadow"
              >
                Register
              </a>
            </div>
          </div>
        )}
      </header>

      {/* Hero */}
      <section id="home" className="relative overflow-hidden">
        <div className="absolute inset-0 bg-gradient-to-br from-orange-50 via-white to-blue-50" />
        <div className="relative max-w-7xl mx-auto px-4 py-20 lg:py-28 grid lg:grid-cols-2 gap-10 items-center">
          <div>
            <h1 className="text-4xl md:text-5xl font-black tracking-tight leading-tight">
              Fast feet. Smart play. <span className="text-orange-600">Futsal</span> for Every Kid.
            </h1>
            <p className="mt-4 text-neutral-600 max-w-prose">
              Train with experienced coaches, sharpen your ball control, and compete in our high-energy events.
              Our Christmas Frosty League runs <strong>Dec 26 – Dec 31</strong> at the Beale Sports Center in Chesterfield.
            </p>
            <div className="mt-6 flex flex-wrap gap-3">
              <a href="#register" className="rounded-2xl px-5 py-3 bg-orange-600 text-white font-semibold shadow hover:bg-orange-700">Register Now</a>
              <a href="#league" className="rounded-2xl px-5 py-3 border border-neutral-300 hover:border-neutral-400">Learn More</a>
            </div>
            <ul className="mt-6 text-sm text-neutral-600 grid gap-2">
              <li>• Free facility entry (food pantry partnership—bring a non-perishable item)</li>
              <li>• Awards: Champions shirts & medals, Golden Boot & Golden Glove</li>
              <li>• Multiple divisions; 3+ guaranteed games</li>
            </ul>
          </div>
          <div className="relative">
            <div className="aspect-[4/3] rounded-3xl overflow-hidden shadow-xl bg-neutral-200">
              {/* Replace src with your image */}
              <img
                src="https://images.unsplash.com/photo-1546519638-68e109498ffc?q=80&w=1600&auto=format&fit=crop"
                alt="Futsal training"
                className="w-full h-full object-cover"
              />
            </div>
          </div>
        </div>
      </section>

      {/* About */}
      <section id="about" className="py-16">
        <div className="max-w-7xl mx-auto px-4 grid lg:grid-cols-2 gap-10 items-start">
          <div className="prose max-w-none">
            <h2 className="text-3xl font-extrabold tracking-tight">About 67FA</h2>
            <p className="text-neutral-700">
              67 Futsal Academy delivers high-repetition, high-fun sessions built around technique, vision, and decision making.
              We train boys and girls across multiple age groups and host leagues and tournaments in the St. Louis area.
            </p>
            <ul className="grid gap-2 text-neutral-700">
              <li>• Licensed coaches with futsal and soccer backgrounds</li>
              <li>• Small-sided pedagogy for maximum touches</li>
              <li>• Options for team training, small groups, and private sessions</li>
            </ul>
          </div>
          <div className="grid sm:grid-cols-3 gap-4">
            {[
              { label: "Players Trained", value: "250+" },
              { label: "Sessions/Week", value: "4" },
              { label: "Avg. Touches/Session", value: "2–3k" },
            ].map((stat) => (
              <div key={stat.label} className="bg-white rounded-2xl shadow-sm border border-neutral-200 p-6 text-center">
                <div className="text-3xl font-black text-orange-600">{stat.value}</div>
                <div className="mt-1 text-sm text-neutral-500">{stat.label}</div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Programs */}
      <section id="programs" className="py-16 bg-white">
        <div className="max-w-7xl mx-auto px-4">
          <h2 className="text-3xl font-extrabold tracking-tight">Programs</h2>
          <div className="mt-8 grid md:grid-cols-3 gap-6">
            {[
              {
                title: "Academy Training",
                body: "Foundational futsal skills—first touch, passing angles, quick finishing.",
                bullets: ["Ages 7–15", "60–75 min", "Weekly blocks"],
              },
              {
                title: "Team Sessions",
                body: "Bring your full squad for tactical futsal and game model work.",
                bullets: ["Clubs & schools", "Custom plans", "Match analysis"],
              },
              {
                title: "Clinics & Camps",
                body: "Schools-out and holiday intensives focused on fast improvement.",
                bullets: ["1–3 days", "Small groups", "High reps"],
              },
            ].map((card) => (
              <div key={card.title} className="bg-white rounded-2xl shadow-sm border border-neutral-200 p-6">
                <h3 className="font-bold text-lg">{card.title}</h3>
                <p className="mt-2 text-sm text-neutral-600">{card.body}</p>
                <ul className="mt-3 text-sm text-neutral-700 grid gap-1">
                  {card.bullets.map((b) => (
                    <li key={b}>• {b}</li>
                  ))}
                </ul>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Christmas League */}
      <section id="league" className="py-16 bg-neutral-50">
        <div className="max-w-7xl mx-auto px-4">
          <div className="flex items-start justify-between gap-6 flex-wrap">
            <div>
              <h2 className="text-3xl font-extrabold tracking-tight">Christmas Frosty Futsal League</h2>
              <p className="mt-2 text-neutral-700 max-w-prose">
                High-level competition with a lot of fun. Champions receive a commemorative shirt and medals.
                Second and third place receive medals. Individual awards for Golden Boot and Golden Glove.
              </p>
              <ul className="mt-3 text-sm text-neutral-700 grid gap-1">
                <li>• Dates: Dec 26 – Dec 31</li>
                <li>• Venue: Beale Sports Center, Chesterfield, MO</li>
                <li>• Divisions: 2014–2017 boys & girls (more on demand)</li>
                <li>• Facility entry: Free (please bring a pantry donation)</li>
              </ul>
              <div className="mt-4 flex gap-3">
                <a href="#register" className="rounded-2xl px-5 py-3 bg-orange-600 text-white font-semibold shadow hover:bg-orange-700">Team Registration</a>
                <a href="#rules" className="rounded-2xl px-5 py-3 border border-neutral-300 hover:border-neutral-400">Rules & Format</a>
              </div>
            </div>
            <div className="bg-white rounded-2xl shadow-sm border border-neutral-200 p-6 w-full max-w-md">
              <h3 className="font-bold">Entry Fees (example)</h3>
              <ul className="mt-2 text-sm text-neutral-700 grid gap-1">
                <li>• Team: $350 (3 games guaranteed)</li>
                <li>• Referee fee: Included</li>
                <li>• Roster: 8–12 players</li>
              </ul>
              <p className="mt-3 text-xs text-neutral-500">* Adjust numbers to your actual pricing.</p>
            </div>
          </div>
        </div>
      </section>

      {/* Schedule */}
      <section id="schedule" className="py-16">
        <div className="max-w-7xl mx-auto px-4">
          <h2 className="text-3xl font-extrabold tracking-tight">Sample Schedule</h2>
          <div className="mt-6 overflow-x-auto">
            <table className="w-full text-sm border-separate border-spacing-y-2">
              <thead>
                <tr className="text-left text-neutral-500">
                  <th className="py-2 pr-4">Date</th>
                  <th className="py-2 pr-4">Court</th>
                  <th className="py-2 pr-4">Time</th>
                  <th className="py-2 pr-4">Division</th>
                  <th className="py-2 pr-4">Match</th>
                </tr>
              </thead>
              <tbody>
                {[
                  { d: "Thu, Dec 26", c: "Court 1", t: "10:30 AM", div: "2016 Boys", m: "Team A vs Team B" },
                  { d: "Thu, Dec 26", c: "Court 2", t: "11:15 AM", div: "2016 Girls", m: "Team C vs Team D" },
                  { d: "Fri, Dec 27", c: "Court 1", t: "6:00 PM", div: "2015 Boys", m: "Team E vs Team F" },
                ].map((row, i) => (
                  <tr key={i} className="bg-white rounded-xl shadow-sm border border-neutral-200">
                    <td className="py-3 px-4 rounded-l-xl">{row.d}</td>
                    <td className="py-3 px-4">{row.c}</td>
                    <td className="py-3 px-4">{row.t}</td>
                    <td className="py-3 px-4">{row.div}</td>
                    <td className="py-3 px-4 rounded-r-xl">{row.m}</td>
                  </tr>
                ))}
              </tbody>
            </table>
          </div>
          <p className="mt-3 text-xs text-neutral-500">We’ll post full fixtures after registration closes.</p>
        </div>
      </section>

      {/* Register */}
      <section id="register" className="py-16 bg-white">
        <div className="max-w-7xl mx-auto px-4 grid lg:grid-cols-2 gap-10 items-center">
          <div>
            <h2 className="text-3xl font-extrabold tracking-tight">Register</h2>
            <p className="mt-2 text-neutral-700 max-w-prose">
              Ready to play? Use the button to open our registration form. If your club needs an invoice or W-9, contact us below and we’ll handle it.
            </p>
            <div className="mt-5 flex flex-wrap gap-3">
              {/* Replace with your real form link (Formspree, Google Form, GotSport, etc.) */}
              <a href="https://forms.gle/replace-with-your-form" target="_blank" rel="noreferrer" className="rounded-2xl px-5 py-3 bg-orange-600 text-white font-semibold shadow hover:bg-orange-700">Open Registration Form</a>
              <a href="#contact" className="rounded-2xl px-5 py-3 border border-neutral-300 hover:border-neutral-400">Request Invoice</a>
            </div>
          </div>
          <div className="bg-neutral-50 rounded-2xl border border-neutral-200 p-6">
            <h3 className="font-bold">What you’ll need</h3>
            <ul className="mt-2 text-sm text-neutral-700 grid gap-1">
              <li>• Team name & division</li>
              <li>• Coach/manager contact</li>
              <li>• Approx. roster size</li>
              <li>• Preferred days/times</li>
            </ul>
          </div>
        </div>
      </section>

      {/* Rules */}
      <section id="rules" className="py-16">
        <div className="max-w-7xl mx-auto px-4">
          <h2 className="text-3xl font-extrabold tracking-tight">Rules & Format (editable)</h2>
          <ul className="mt-4 text-sm text-neutral-700 grid gap-2">
            <li>• 5v5 including GK, size 3–4 futsal ball</li>
            <li>• Running clock 2x20’ (festival format optional)</li>
            <li>• No headers, accumulated fouls per FIFA Futsal</li>
            <li>• Shin guards & indoor flats required</li>
            <li>• Tiebreakers: GD → Goals For → Head-to-Head → PKs</li>
          </ul>
        </div>
      </section>

      {/* Contact */}
      <section id="contact" className="py-16 bg-neutral-50">
        <div className="max-w-7xl mx-auto px-4 grid lg:grid-cols-2 gap-10">
          <div>
            <h2 className="text-3xl font-extrabold tracking-tight">Contact</h2>
            <p className="mt-2 text-neutral-700 max-w-prose">
              Questions about training, scheduling, or facility partnerships? Reach out—we’re fast to reply.
            </p>
            <div className="mt-6 grid gap-3 text-sm">
              <a href="mailto:hello@67fa.com" className="inline-flex items-center gap-2">
                <span className="w-8 h-8 rounded-xl bg-orange-100 grid place-items-center">📧</span>
                hello@67fa.com
              </a>
              <a href="tel:+1633XXXXXXX" className="inline-flex items-center gap-2">
                <span className="w-8 h-8 rounded-xl bg-orange-100 grid place-items-center">📞</span>
                (633) 000-0000
              </a>
              <div className="inline-flex items-center gap-2">
                <span className="w-8 h-8 rounded-xl bg-orange-100 grid place-items-center">📍</span>
                Beale Sports Center, Chesterfield, MO
              </div>
            </div>
          </div>
          <div className="bg-white rounded-2xl shadow-sm border border-neutral-200 p-6">
            <h3 className="font-bold">Partnerships</h3>
            <p className="mt-2 text-sm text-neutral-700">
              Facilities and clubs: let’s collaborate on leagues, training blocks, and events. We can provide coaches, goals, timing equipment, and full league ops.
            </p>
            <a href="mailto:partners@67fa.com" className="mt-4 inline-block rounded-2xl px-5 py-3 bg-orange-600 text-white font-semibold shadow hover:bg-orange-700">Email Partnerships</a>
          </div>
        </div>
      </section>

      {/* Gallery (optional) */}
      <section id="gallery" className="py-16">
        <div className="max-w-7xl mx-auto px-4">
          <h2 className="text-3xl font-extrabold tracking-tight">Gallery</h2>
          <div className="mt-6 grid sm:grid-cols-2 lg:grid-cols-3 gap-4">
            {[1,2,3,4,5,6].map((i) => (
              <div key={i} className="aspect-[4/3] overflow-hidden rounded-2xl border border-neutral-200 bg-neutral-100">
                <img
                  src={`https://picsum.photos/seed/futsal-${i}/800/600`}
                  alt="Futsal"
                  className="w-full h-full object-cover hover:scale-105 transition-transform"
                />
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="border-t border-neutral-200">
        <div className="max-w-7xl mx-auto px-4 py-10 grid md:grid-cols-3 gap-8 items-start">
          <div>
            <div className="font-black text-lg">67 Futsal Academy</div>
            <p className="mt-2 text-sm text-neutral-600 max-w-prose">
              Building confident players through futsal—quick decisions, faster feet, and smarter play.
            </p>
          </div>
          <div className="text-sm">
            <div className="font-semibold">Site</div>
            <ul className="mt-2 grid gap-1 text-neutral-600">
              {navItems.map((n) => (
                <li key={n.href}><a href={n.href} className="hover:text-orange-600">{n.label}</a></li>
              ))}
            </ul>
          </div>
          <div className="text-sm">
            <div className="font-semibold">Follow</div>
            <ul className="mt-2 grid gap-1 text-neutral-600">
              <li><a href="https://instagram.com/yourhandle" target="_blank" rel="noreferrer" className="hover:text-orange-600">Instagram</a></li>
              <li><a href="https://facebook.com/yourpage" target="_blank" rel="noreferrer" className="hover:text-orange-600">Facebook</a></li>
            </ul>
          </div>
        </div>
        <div className="text-center text-xs text-neutral-500 pb-8">© {new Date().getFullYear()} 67 Futsal Academy. All rights reserved.</div>
      </footer>

      {/* SEO JSON-LD (edit org info) */}
      <script type="application/ld+json" dangerouslySetInnerHTML={{ __html: JSON.stringify({
        "@context": "https://schema.org",
        "@type": "SportsOrganization",
        name: "67 Futsal Academy",
        url: "https://67fa.com",
        address: {
          "@type": "PostalAddress",
          addressLocality: "Chesterfield",
          addressRegion: "MO",
          addressCountry: "US",
        },
        sameAs: [
          "https://instagram.com/yourhandle",
          "https://facebook.com/yourpage"
        ]
      }) }} />
    </div>
  );
}
