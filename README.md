import React, { useEffect, useState } from 'react';

export default function UCalgarySUERevamp() {
  const serif = 'Georgia, Cambria, "Times New Roman", Times, serif';
  const sans = 'Inter, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif';

  const brand = {
    primary: '#2F5E4E',
    primaryHover: '#3D6B5B',
    primaryDeep: '#20342C',
    background: '#F4F2EC',
    surface: '#FCFBF8',
    surfaceWarm: '#F8F6F1',
    surfaceAlt: '#EEF3EF',
    border: '#DDD8CD',
    borderGreen: '#C8D6CF',
    text: '#1F2933',
    muted: '#5B6470',
    accentSoft: '#DCE7E1',
    accentPale: '#E7EFEA',
  };

  const stats = [
    { label: 'Founded', value: '1982' },
    { label: 'Student Resources', value: '200–500' },
    { label: 'Flagship Events', value: 'Year-Round' },
    { label: 'Department Reach', value: 'Undergraduate Economics', valueClassName: 'text-[1.45rem] md:text-[1.7rem] leading-[1.12]' },
    { label: 'Industry Engagement', value: 'Employer-Facing', valueClassName: 'text-[1.55rem] md:text-[1.85rem] leading-[1.12]' },
    { label: 'Academic Support', value: 'Exam Bank + Guides', valueClassName: 'text-[1.45rem] md:text-[1.7rem] leading-[1.12]' },
    { label: 'Leadership Pipeline', value: 's', valueClassName: 'text-[1.45rem] md:text-[1.7rem] leading-[1.12]' },
    { label: 'Leadership Pipeline', value: 'Student-Led', valueClassName: 'text-[1.7rem] md:text-[2rem] leading-[1.1]' },
    { label: 'Campus Presence', value: 'Visible Year-Round', valueClassName: 'text-[1.45rem] md:text-[1.7rem] leading-[1.12]' },
  ];

  const pillars = [
    {
      title: 'Academic Support',
      text: 'S.U.E. serves the academic goals of economics students through an exam bank, degree planning tools, course-level guidance, and practical resources for every stage of the degree.',
    },
    {
      title: 'Career Preparation',
      text: 'From Industry Night and Talkonomics to resume clinics and information sessions, S.U.E. helps students build professional confidence and real industry exposure.',
    },
    {
      title: 'Department Community',
      text: 'S.U.E. builds an open and accessible community within the Economics department by connecting students with peers, faculty, and external industry associations.',
    },
  ];

  const quickLinks = ['Events', 'Student Resources', 'Industry Night', 'Contact', 'Join SUE'];

  const heroUpcomingEvents = [
    {
      title: 'Industry Night 2026',
      date: 'March 2026',
      description: 'A flagship networking and professional development event connecting economics students with industry professionals and employers.',
    },
    {
      title: 'Talkonomics #7',
      date: 'Upcoming',
      description: 'A thought leadership series bringing current economic issues, policy questions, and public discourse into the student community.',
    },
    {
      title: 'Excel Workshop Series',
      date: 'Semester Series',
      description: 'Applied technical workshops helping students strengthen analytical, spreadsheet, and professional skills.',
    },
  ];

  const resources = [
    {
      title: 'Academic Resources',
      text: 'An extensive exam bank with practice midterms and finals spanning 200-level to 500-level economics courses.',
      cta: 'Access Exam Bank',
    },
    {
      title: 'EconPath',
      text: 'A student-led, student-centric academic and career navigation tool designed to support students at any point in their economics journey.',
      cta: 'Explore EconPath',
    },
    {
      title: 'Degree Planning',
      text: 'A guided degree planning resource to help students understand possible paths while encouraging consultation with advisors and official UCalgary resources.',
      cta: 'View Degree Paths',
    },
  ];

  const updates = [
    {
      title: "We're growing our Team!",
      type: 'News',
      text: 'Highlight recruitment updates, leadership opportunities, and ways for students to get involved in building the economics community.',
    },
    {
      title: 'Talkonomics #7: Canada in the Age of Electricity',
      type: 'Featured Event',
      text: 'Showcase thought leadership events that connect economics students to current policy, markets, and national conversations.',
    },
  ];

  const sponsors = [
    {
      title: 'A professional sponsor-facing presence',
      text: 'Retain S.U.E.’s student mission while presenting a clearer institutional image for sponsors, employers, and alumni supporters.',
    },
    {
      title: 'Clear proof of relevance',
      text: 'The landing page should immediately communicate longevity, student value, flagship initiatives, and consistent departmental engagement.',
    },
    {
      title: 'Trust through structure',
      text: 'A better homepage gives outside partners a fast understanding of what S.U.E. does, why it matters, and how they can support it.',
    },
  ];

  const navLink = {
    color: 'inherit',
    textDecoration: 'none',
  };

  const sectionEyebrow = {
    color: brand.primary,
    fontSize: '0.76rem',
    letterSpacing: '0.32em',
fontWeight: 700,
  };

  const cardShadow = '0 8px 24px rgba(47,94,78,0.06)';
  const metricCardMinHeight = '168px';
  const eventCardBodyMinHeight = '172px';
  const [activeEvent, setActiveEvent] = useState(0);

  useEffect(() => {
    const interval = window.setInterval(() => {
      setActiveEvent((prev) => (prev + 1) % heroUpcomingEvents.length);
    }, 4000);
    return () => window.clearInterval(interval);
  }, [heroUpcomingEvents.length]);

  const currentEvent = heroUpcomingEvents[activeEvent];

  return (
    <div className="min-h-screen" style={{ backgroundColor: brand.background, color: brand.text, fontFamily: sans }}>
      <header
        className="sticky top-0 z-50 border-b backdrop-blur"
        style={{ borderColor: brand.border, backgroundColor: 'rgba(252, 251, 248, 0.96)' }}
      >
        <div className="mx-auto flex max-w-7xl items-center justify-between px-6 py-4">
          <div>
            <div style={sectionEyebrow}>University of Calgary</div>
            <div className="text-xl font-semibold tracking-[0.02em]" style={{ color: brand.text, fontFamily: serif }}>
              Society of Undergraduates in Economics
            </div>
          </div>

          <nav className="hidden gap-6 text-sm md:flex" style={{ color: brand.muted }}>
            {[
              ['#about', 'About'],
              ['#resources', 'Resources'],
              ['#updates', 'News'],
              ['#events', 'Events'],
              ['#partners', 'Sponsors'],
              ['#team', 'Team'],
            ].map(([href, label]) => (
              <a
                key={label}
                href={href}
                className="transition"
                style={navLink}
                onMouseEnter={(e) => {
                  e.currentTarget.style.color = brand.primary;
                }}
                onMouseLeave={(e) => {
                  e.currentTarget.style.color = 'inherit';
                }}
              >
                {label}
              </a>
            ))}
          </nav>

          <div className="flex gap-3">
            <button
              className="rounded-sm border px-4 py-2 text-sm font-medium uppercase tracking-[0.08em] transition"
              style={{ borderColor: brand.primary, color: brand.primary, backgroundColor: 'transparent' }}
              onMouseEnter={(e) => {
                e.currentTarget.style.backgroundColor = brand.accentSoft;
              }}
              onMouseLeave={(e) => {
                e.currentTarget.style.backgroundColor = 'transparent';
              }}
            >
              Sponsor S.U.E.
            </button>
            <button
              className="rounded-sm px-4 py-2 text-sm font-semibold uppercase tracking-[0.08em] text-white shadow-lg transition"
              style={{ backgroundColor: brand.primary }}
              onMouseEnter={(e) => {
                e.currentTarget.style.backgroundColor = brand.primaryHover;
              }}
              onMouseLeave={(e) => {
                e.currentTarget.style.backgroundColor = brand.primary;
              }}
            >
              Join Now
            </button>
          </div>
        </div>
      </header>

      <section
        className="relative overflow-hidden border-b"
        style={{
          borderColor: brand.border,
          background: 'linear-gradient(135deg, #FCFBF8 0%, #F4F2EC 42%, #E7EFEA 100%)',
        }}
      >
        <div
          className="absolute inset-0"
          style={{
            background:
              'radial-gradient(circle at top right, rgba(47,94,78,0.18), transparent 28%), radial-gradient(circle at left, rgba(47,94,78,0.08), transparent 22%), linear-gradient(to bottom, rgba(47,94,78,0.03), rgba(47,94,78,0))',
          }}
        />

        <div className="mx-auto max-w-7xl px-6 pt-8 pb-16 lg:pt-10 lg:pb-20">
          <div
            className="relative z-10 mb-8 border px-4 py-3"
            style={{ borderColor: brand.borderGreen, backgroundColor: brand.surfaceWarm, boxShadow: cardShadow }}
          >
            <div className="flex items-center gap-2 overflow-x-auto whitespace-nowrap">
              <div
                className="pr-3 text-[0.65rem] font-semibold uppercase tracking-[0.28em] whitespace-nowrap"
                style={{ color: brand.primary }}
              >
                Quick Access
              </div>
              {quickLinks.map((feature) => (
                <button
                  key={feature}
                  className="whitespace-nowrap rounded-sm border px-3 py-2 text-[0.68rem] font-medium uppercase tracking-[0.08em] transition md:flex-1"
                  style={{ borderColor: brand.borderGreen, backgroundColor: brand.surface, color: brand.text }}
                  onMouseEnter={(e) => {
                    e.currentTarget.style.backgroundColor = brand.surfaceAlt;
                  }}
                  onMouseLeave={(e) => {
                    e.currentTarget.style.backgroundColor = brand.surface;
                  }}
                >
                  {feature}
                </button>
              ))}
            </div>
          </div>

          <div className="relative z-10 grid items-start gap-10 lg:grid-cols-[1.15fr_0.85fr]">
            <div>
              <div
                className="mb-4 inline-flex rounded-sm border px-4 py-1 text-xs font-semibold uppercase tracking-[0.32em]"
                style={{ borderColor: brand.borderGreen, backgroundColor: brand.surface, color: brand.primary }}
              >
                Since 1982 • Student-led • Economics at UCalgary
              </div>

              <h1
                className="max-w-4xl text-5xl font-semibold leading-[1.06] tracking-[-0.02em] md:text-6xl"
                style={{ color: brand.text, fontFamily: serif }}
              >
                A stronger digital home for the economics student body at UCalgary.
              </h1>

              <p className="mt-6 max-w-2xl text-lg leading-8" style={{ color: brand.muted }}>
                The Society of Undergraduates in Economics serves the academic and career goals of its members by creating an open and accessible community within the Economics department while connecting students to faculty, industry, and opportunity.
              </p>

              <div className="mt-10 grid max-w-5xl grid-cols-2 gap-4 md:grid-cols-4">
                {stats.map((item) => {
                  const valueClassName = item.valueClassName ?? 'text-[1.8rem] md:text-[2.05rem] leading-[1.08]';

                  return (
                    <div
                      key={item.label}
                      className="rounded-md border p-4 md:p-5"
                      style={{
                        borderColor: brand.borderGreen,
                        backgroundColor: brand.surfaceWarm,
                        boxShadow: cardShadow,
                        minHeight: metricCardMinHeight,
                        display: 'flex',
                        flexDirection: 'column',
                        justifyContent: 'space-between',
                      }}
                    >
                      <div
                        className={`${valueClassName} font-semibold tracking-[-0.02em] break-words`}
                        style={{ color: brand.text, fontFamily: serif }}
                      >
                        {item.value}
                      </div>
                      <div className="mt-2 text-[0.95rem] leading-6" style={{ color: brand.muted }}>
                        {item.label}
                      </div>
                    </div>
                  );
                })}
              </div>
            </div>

            <div
              className="border p-4"
              style={{ borderColor: brand.primary, backgroundColor: brand.surface, boxShadow: '0 16px 40px rgba(47,94,78,0.10)' }}
            >
              <div className="border p-6" style={{ borderColor: brand.primary, backgroundColor: brand.surfaceAlt }}>
                <div
                  className="mb-6 inline-flex rounded-sm border px-4 py-1 text-xs font-semibold uppercase tracking-[0.32em]"
                  style={{ borderColor: brand.borderGreen, backgroundColor: brand.surface, color: brand.primary }}
                >
                  Upcoming Events
                </div>

                <div className="overflow-hidden rounded-sm border" style={{ borderColor: brand.borderGreen, backgroundColor: brand.surface }}>
                  <div
                    className="h-44 border-b transition-all duration-500"
                    style={{
                      borderColor: brand.borderGreen,
                      background: `linear-gradient(135deg, ${brand.accentSoft} 0%, ${brand.surfaceAlt} 100%)`,
                    }}
                  />
                  <div className="p-5 md:p-6">
                    <div className="text-[0.72rem] font-semibold uppercase tracking-[0.18em]" style={{ color: brand.muted }}>
                      {currentEvent.date}
                    </div>
                    <div className="mt-2 text-[1.9rem] font-semibold leading-[1.12] tracking-[-0.02em] text-balance" style={{ color: brand.text, fontFamily: serif }}>
                      {currentEvent.title}
                    </div>
                    <p className="mt-3 text-[0.98rem] leading-7" style={{ color: brand.muted, minHeight: eventCardBodyMinHeight }}>
                      {currentEvent.description}
                    </p>

                    <div className="mt-5 flex gap-2">
                      {heroUpcomingEvents.map((_, index) => (
                        <button
                          key={index}
                          aria-label={`Go to event ${index + 1}`}
                          className="h-2.5 w-8 rounded-sm transition"
                          style={{
                            backgroundColor: index === activeEvent ? brand.primary : brand.accentSoft,
                            opacity: index === activeEvent ? 1 : 0.8,
                          }}
                          onClick={() => setActiveEvent(index)}
                        />
                      ))}
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section id="about" className="mx-auto max-w-7xl px-6 py-20">
        <div className="max-w-3xl">
          <div style={sectionEyebrow}>About S.U.E.</div>
          <h2
            className="mt-3 text-3xl font-semibold leading-tight tracking-[-0.02em] md:text-4xl"
            style={{ color: brand.text, fontFamily: serif }}
          >
            Keeping the substance of the current site, but presenting it with more clarity and authority.
          </h2>
          <p className="mt-4 max-w-2xl leading-8" style={{ color: brand.muted }}>
            This version preserves the real mandate already on the website: S.U.E. supports academic success, career development, and a welcoming departmental community. The difference is that the content is now framed in a cleaner, more elegant way that feels credible to students and polished to external stakeholders.
          </p>
        </div>

        <div className="mt-10 grid gap-6 md:grid-cols-3">
          {pillars.map((item) => (
            <div
              key={item.title}
              className="rounded-lg border p-7"
              style={{ borderColor: brand.borderGreen, backgroundColor: brand.surfaceWarm, boxShadow: cardShadow }}
            >
              <h3 className="text-xl font-semibold tracking-[-0.01em]" style={{ color: brand.text, fontFamily: serif }}>
                {item.title}
              </h3>
              <p className="mt-3 leading-7" style={{ color: brand.muted }}>
                {item.text}
              </p>
            </div>
          ))}
        </div>
      </section>

      <section id="resources" className="border-y" style={{ borderColor: brand.border, backgroundColor: brand.surfaceAlt }}>
        <div className="mx-auto max-w-7xl px-6 py-20">
          <div className="max-w-3xl">
            <div style={sectionEyebrow}>First-year and returning student support</div>
            <h2
              className="mt-3 text-3xl font-semibold leading-tight tracking-[-0.02em] md:text-4xl"
              style={{ color: brand.text, fontFamily: serif }}
            >
              The most useful landing-page resources should stay front and center.
            </h2>
            <p className="mt-4 max-w-2xl leading-8" style={{ color: brand.muted }}>
              The current homepage already points students toward academic resources, EconPath, and degree planning. Those are strong anchors. In the redesign, they should remain immediately visible, but with better hierarchy, clearer grouping, and stronger calls to action.
            </p>
          </div>

          <div className="mt-10 grid gap-6 md:grid-cols-3">
            {resources.map((item) => (
              <div
                key={item.title}
                className="rounded-lg border p-6"
                style={{ borderColor: brand.borderGreen, backgroundColor: brand.surfaceWarm, boxShadow: cardShadow }}
              >
                <div className="text-sm font-semibold uppercase tracking-[0.32em]" style={{ color: brand.primary }}>
                  Student Resource
                </div>
                <h3 className="mt-3 text-2xl font-semibold tracking-[-0.01em]" style={{ color: brand.text, fontFamily: serif }}>
                  {item.title}
                </h3>
                <p className="mt-3 leading-7" style={{ color: brand.muted }}>
                  {item.text}
                </p>
                <button
                  className="mt-6 rounded-sm px-4 py-2 text-sm font-semibold uppercase tracking-[0.08em] text-white transition"
                  style={{ backgroundColor: brand.primary }}
                  onMouseEnter={(e) => {
                    e.currentTarget.style.backgroundColor = brand.primaryHover;
                  }}
                  onMouseLeave={(e) => {
                    e.currentTarget.style.backgroundColor = brand.primary;
                  }}
                >
                  {item.cta}
                </button>
              </div>
            ))}
          </div>
        </div>
      </section>

      <section id="updates" className="mx-auto max-w-7xl px-6 py-20">
        <div className="flex flex-col gap-4 md:flex-row md:items-end md:justify-between">
          <div className="max-w-3xl">
            <div style={sectionEyebrow}>News and updates</div>
            <h2
              className="mt-3 text-3xl font-semibold leading-tight tracking-[-0.02em] md:text-4xl"
              style={{ color: brand.text, fontFamily: serif }}
            >
              Keep the homepage active with live momentum.
            </h2>
            <p className="mt-4 max-w-2xl leading-8" style={{ color: brand.muted }}>
              The current site already signals momentum through team recruitment and Talkonomics. That is good. The redesign should turn those moments into a sharper news band that immediately shows S.U.E. is active, growing, and intellectually engaged.
            </p>
          </div>
          <button
            className="rounded-sm border px-5 py-3 font-semibold uppercase tracking-[0.08em] transition"
            style={{ borderColor: brand.border, backgroundColor: brand.surface, color: brand.text }}
            onMouseEnter={(e) => {
              e.currentTarget.style.backgroundColor = brand.surfaceAlt;
            }}
            onMouseLeave={(e) => {
              e.currentTarget.style.backgroundColor = brand.surface;
            }}
          >
            See All Updates
          </button>
        </div>

        <div className="mt-10 grid gap-6 md:grid-cols-2">
          {updates.map((item) => (
            <div
              key={item.title}
              className="rounded-lg border p-7"
              style={{ borderColor: brand.borderGreen, backgroundColor: brand.surfaceWarm, boxShadow: cardShadow }}
            >
              <div className="text-sm font-semibold uppercase tracking-[0.32em]" style={{ color: brand.primary }}>
                {item.type}
              </div>
              <h3 className="mt-3 text-2xl font-semibold tracking-[-0.01em]" style={{ color: brand.text, fontFamily: serif }}>
                {item.title}
              </h3>
              <p className="mt-3 leading-7" style={{ color: brand.muted }}>
                {item.text}
              </p>
            </div>
          ))}
        </div>
      </section>

      <section
        id="events"
        className="border-y text-white"
        style={{ borderColor: brand.border, background: 'linear-gradient(180deg, #20342C 0%, #182028 100%)' }}
      >
        <div className="mx-auto max-w-7xl px-6 py-20">
          <div className="flex flex-col gap-4 md:flex-row md:items-end md:justify-between">
            <div>
              <div className="text-sm font-semibold uppercase tracking-[0.32em]" style={{ color: '#C7DED4' }}>
                Events and visibility
              </div>
              <h2 className="mt-3 text-3xl font-semibold leading-tight tracking-[-0.02em] md:text-4xl" style={{ fontFamily: serif }}>
                Preserve the events focus, but make it feel flagship-level.
              </h2>
            </div>
            <button
              className="rounded-sm border px-5 py-3 font-semibold uppercase tracking-[0.08em] text-white transition"
              style={{ borderColor: 'rgba(220,231,225,0.18)' }}
              onMouseEnter={(e) => {
                e.currentTarget.style.backgroundColor = 'rgba(220,231,225,0.08)';
              }}
              onMouseLeave={(e) => {
                e.currentTarget.style.backgroundColor = 'transparent';
              }}
            >
              See All Events
            </button>
          </div>

          <div className="mt-10 grid gap-6 md:grid-cols-3">
            {[
              { date: 'Live Calendar', title: 'Events Calendar', type: 'Always Available' },
              { date: '2026', title: 'Industry Night 2026', type: 'Flagship Event' },
              { date: 'Series', title: 'Talkonomics', type: 'Thought Leadership' },
            ].map((event) => (
              <div
                key={event.title}
                className="rounded-lg border p-6"
                style={{ borderColor: 'rgba(220,231,225,0.18)', backgroundColor: 'rgba(220,231,225,0.08)' }}
              >
                <div className="text-sm uppercase tracking-[0.22em]" style={{ color: '#AEB9B0' }}>
                  {event.type}
                </div>
                <div className="mt-4 text-3xl font-semibold tracking-[-0.01em]" style={{ color: '#C7DED4', fontFamily: serif }}>
                  {event.date}
                </div>
                <div className="mt-2 text-xl font-medium" style={{ fontFamily: serif }}>
                  {event.title}
                </div>
                <p className="mt-3" style={{ color: '#D5DCE2' }}>
                  Structured event presentation with stronger promotion, registration visibility, and clearer strategic importance.
                </p>
              </div>
            ))}
          </div>
        </div>
      </section>

      <section id="partners" className="mx-auto max-w-7xl px-6 py-20">
        <div className="max-w-3xl">
          <div style={sectionEyebrow}>Sponsor and partner appeal</div>
          <h2
            className="mt-3 text-3xl font-semibold leading-tight tracking-[-0.02em] md:text-4xl"
            style={{ color: brand.text, fontFamily: serif }}
          >
            Keep the same identity, but make it stronger for external audiences.
          </h2>
          <p className="mt-4 max-w-2xl leading-8" style={{ color: brand.muted }}>
            The current site is clearly useful for students, but the design language should also signal heritage, credibility, and academic seriousness. This revamp keeps the student purpose intact while making the homepage more persuasive for sponsors, faculty, alumni, and employers.
          </p>
        </div>

        <div className="mt-10 grid gap-6 md:grid-cols-3">
          {sponsors.map((item) => (
            <div
              key={item.title}
              className="rounded-lg border p-7"
              style={{ borderColor: brand.borderGreen, backgroundColor: brand.surfaceWarm, boxShadow: cardShadow }}
            >
              <h3 className="text-xl font-semibold tracking-[-0.01em]" style={{ color: brand.text, fontFamily: serif }}>
                {item.title}
              </h3>
              <p className="mt-3 leading-7" style={{ color: brand.muted }}>
                {item.text}
              </p>
            </div>
          ))}
        </div>
      </section>

      <section id="team" className="border-t" style={{ backgroundColor: brand.surfaceAlt, borderColor: brand.border }}>
        <div className="mx-auto max-w-7xl px-6 py-20">
          <div className="grid gap-8 lg:grid-cols-[1fr_1fr]">
            <div>
              <div style={sectionEyebrow}>Leadership and continuity</div>
              <h2
                className="mt-3 text-3xl font-semibold leading-tight tracking-[-0.02em] md:text-4xl"
                style={{ color: brand.text, fontFamily: serif }}
              >
                Retain the team structure, including past leadership, but present it more professionally.
              </h2>
              <p className="mt-4 max-w-xl leading-8" style={{ color: brand.muted }}>
                The current site already documents present and past teams, which is a credibility advantage. The redesign should elevate that by using more polished executive profiles, cleaner archives, and stronger continuity between annual teams.
              </p>
            </div>

            <div className="grid grid-cols-2 gap-4">
              {['Team of 2025–2026', 'Past Team 2024–2025', 'Past Team 2023–2024', 'Past Team 2022–2023'].map((role) => (
                <div
                  key={role}
                  className="rounded-md border p-5"
                  style={{ borderColor: brand.borderGreen, backgroundColor: brand.surfaceWarm, boxShadow: cardShadow }}
                >
                  <div
                    className="h-24 rounded-sm border"
                    style={{
                      background: `linear-gradient(135deg, ${brand.accentSoft} 0%, ${brand.surfaceAlt} 100%)`,
                      borderColor: brand.borderGreen,
                    }}
                  />
                  <div className="mt-4 text-lg font-semibold tracking-[-0.01em]" style={{ color: brand.text, fontFamily: serif }}>
                    {role}
                  </div>
                  <div className="text-sm" style={{ color: brand.muted }}>
                    Executive archive, bios, and institutional continuity
                  </div>
                </div>
              ))}
            </div>
          </div>
        </div>
      </section>

      <section className="mx-auto max-w-7xl px-6 pb-20 pt-20">
        <div
          className="rounded-lg border p-8 text-white shadow-xl md:p-10"
          style={{ borderColor: '#6A8C7F', background: 'linear-gradient(90deg, #2F5E4E 0%, #3D6B5B 100%)' }}
        >
          <div className="max-w-3xl">
            <div className="text-sm font-semibold uppercase tracking-[0.32em]" style={{ color: '#DCE7E1' }}>
              Revamp direction
            </div>
            <h2 className="mt-3 text-3xl font-semibold leading-tight tracking-[-0.02em] md:text-4xl" style={{ fontFamily: serif }}>
              Same mission. Same recognizable identity. Stronger presentation.
            </h2>
            <p className="mt-4 text-lg leading-8" style={{ color: '#F3F7F5' }}>
              This version integrates the existing landing-page content directly into the redesign while shifting the visual system toward a more classical green-led palette with serif typography, sharper geometry, and stronger institutional presence.
            </p>
            <div className="mt-8 flex flex-wrap gap-4">
              <button className="rounded-sm bg-white px-5 py-3 font-semibold uppercase tracking-[0.08em]" style={{ color: brand.primary }}>
                Refine Homepage Copy
              </button>
              <button className="rounded-sm border border-white/20 px-5 py-3 font-semibold uppercase tracking-[0.08em] text-white">
                Build Remaining Pages
              </button>
            </div>
          </div>
        </div>
      </section>
    </div>
  );
}
