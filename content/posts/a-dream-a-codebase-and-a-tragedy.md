+++
title = "A Dream, a Codebase, and a Tragedy"
date = 2026-04-03
draft = false
+++

It was the summer of 2023. I was about to start my second year of college when a friend called with an opportunity. She worked at a local tech consultancy and asked if I wanted to intern as a mobile developer for a new CRM they were building.

I didn't think much of it. I went in, interviewed, and got the role.

The office was… interesting. There was one senior engineer handling a mix of client and in-house projects. Let's call him John. He had been there for four years and was deeply embedded in everything the company built. Most of their systems were Laravel applications backed by MySQL. Nothing too exotic.

My job sounded straightforward. Consume their CMS APIs and build a mobile app on top of them.

Or so I thought.

Before we get into that, let's rewind.

---

## The Dream

Back in 2018, the company's founder had a vision to build a CRM that would redefine the space they were targeting. Flexible, powerful, well-designed. Something that could truly stand out.

Around that time, John had just joined the company. The CRM became his responsibility.

And that's how the dream began.

---

## The Codebase

Fast forward to 2023.

The CRM was still under development. There was one live instance running on a VPS, used internally.

When I joined, everything seemed under control. John knew the system inside out. He understood how each subsystem fit together and how to keep things moving.

Then I opened the codebase.

There were no APIs.

Laravel was being used purely with SSR via Blade templates. Not a single proper API layer existed. The only exception was authentication, and even that was a tangled mess of functions stuffed into a single endpoint.

At the time, I assumed this was normal. That this was what production systems looked like.

John guided me through it. He helped me understand how things worked and how I should approach building APIs on top of this structure. I was given a GitHub branch, and I got to work, building endpoints while simultaneously developing the mobile app.

---

## The Tragedy

As my second year came to an end, things at the office began to shift.

People started leaving.

First, the friend who had referred me, the designer behind the mobile app, resigned. Then the HR moved out and went remote.

But none of that compared to what happened next.

John quit.

I wasn't part of the leadership discussions, but the atmosphere changed overnight. The CEO looked tense. Conversations became quieter.

John's responsibilities were handed over to the second-in-command. Let's call him Max.

Max was… different. He wasn't very communicative. He had a surface-level understanding of the system, but not the depth John had. There were multiple knowledge transfer sessions during John's notice period.

Then the notice period ended.

And John was gone.

That's when things started to unravel.

Coding standards slipped.

New developers joined and began making changes without fully understanding the system. Documentation, which was already thin, started disappearing entirely. GitHub commits became vague and inconsistent.

Too many hands. Not enough context.

Core subsystems began to break.

Even something as fundamental as authentication started failing, ironically, while someone was trying to add "Sign in with Google."

Management kept asking for features, and the engineering team kept shipping code without proper reviews.

For instance, the CRM supported a third-party device used to capture data points such as camera and biometrics. The function handling this was over 5,000 lines long.

The database had no integrity constraints. No primary keys, no foreign keys, no indexes.

The data syncing process from third-party devices to the main database was handled by a cron job that ran at midnight. It would sometimes crash with OOM errors, silently. There was no error handling. No try-catch blocks. No monitoring. Nothing.

Meanwhile, I was still working.

For nearly a year, I had been building API endpoints on top of an SSR-based system. My work depended heavily on core subsystems, functions, and flows that were now unstable.

As those subsystems broke,\
so did my APIs.

---

## The Beautiful Aftermath

Fast forward to 2026.

I had left the company. The CRM was still in development when I left. By then, it had around 10 paying clients. I had been moved to other client projects and had minimal involvement with the CRM.

The mobile app?

It never rolled out with all its intended features.

The system had become so fragile that random internet bots would break into the server using an old WordPress plugin vulnerability, something no one wanted to deal with.

Clients would call in with complaints. Outages, data loss, inconsistencies.

I had watched the project slowly come apart, piece by piece. What began as a vision had turned into something unrecognizable.

And yet,

it refused to die.

Somehow, despite everything, it kept running. Requests went through. Data moved. Clients logged in, clicked buttons, and got what they needed.

Behind the scenes, it was chaos. Silent failures. Patches over patches.

But on the surface, it lived.

And maybe that was the beautiful part.

Not that the system was broken.

But that it worked anyway.

Like an old machine held together by habit and hope, it carried on, indifferent to the cracks beneath it.

And standing at a distance, no longer a part of it, I realised something.

The system did not need to be beautiful.

It did not need to be correct.

It only needed to survive.

And for those who used it,

that was enough.
