---
# ============================================================
# SESSION TEMPLATE (use for every session type)
# One file per session, even if it runs more than once.
# Delete nothing: leave unused fields as "" or []
# ============================================================


# ------------------------------------------------------------
# 1. BASICS (required)
# ------------------------------------------------------------

title: "Monday Workshop 2"

# One of: keynote, tutorial, talk, workshop, meeting, social, other
category: "workshop"

# Leave as is
layout: session

# Link to join online (Teams, Zoom...). Leave "" if the session is in person only.
hybrid: ""


# ------------------------------------------------------------
# 2. WHEN AND WHERE (required)
# Times are 24-hour "HH:MM". Days are Monday to Friday, written in full.
# ------------------------------------------------------------

day: "Monday"
start_time: "11:00"
end_time: "12:30"
track: "B"
room: "CLC203 (260)"

# Does the session run again? Add one entry per repeat, in this same file.
# "room" is optional: if you leave it out, the main room above is used.
# No repeats? Keep the line below as it is.
additional_slots: []

# Example with two repeats:
additional_slots:
  - day: "Monday"
    start_time: "13:30"
    end_time: "14:00"
#   - day: "Tuesday"
#     start_time: "16:30"
#     end_time: "18:00"
#     room: "MCS0002"


# ------------------------------------------------------------
# 3. PEOPLE
# Fill only the roles that apply. Names are comma-separated.
# Photos and links must be in the same order as the names.
# Use "" for a missing photo or link so the order stays aligned.
# ------------------------------------------------------------

# Lead (meetings, workshops, socials)
lead: ""
lead_photos: []
lead_links: []

# Instructor (tutorials)
instructor: ""
instructor_photos: []
instructor_links: []

# Facilitator (talks, panels, discussions)
facilitator: ""
facilitator_photos: []
facilitator_links: []

# Speaker (keynotes, talks, vendor sessions)
speaker: ""
speaker_photos: []
speaker_links: []

# Contributors (anyone else involved)
contributor: ""
contributor_photos: []
contributor_links: []

# Are the "photos" above company logos rather than portraits (e.g. vendor sessions)?
# "" = portraits (cropped to a square), "logo" = logos (shown whole on a light tile)
photo_style: ""

# Example (two instructors):
# instructor: "Georg Hager, Thomas Gruber"
# instructor_photos:
#   - "https://hpc.fau.de/files/2023/08/georg-hager-240x320.png"
#   - "assets/images/generic.jpg"
# instructor_links:
#   - "https://hpc.fau.de/person/georg-hager/"
#   - ""


# ------------------------------------------------------------
# 4. AFFILIATION / DELIVERY
# Fill ONLY ONE of the three blocks, whichever fits best.
#   institution: where the people are based (university, lab, company)
#   organiser:   who formally organises or hosts the session
#   supported:   who funds or sponsors it
# ------------------------------------------------------------

institution: ""
institution_logo: ""
institution_link: ""

organiser: ""
organiser_logo: ""
organiser_link: ""

supported: ""
supported_logo: ""
supported_link: ""


# ------------------------------------------------------------
# 5. DESCRIPTION
# Keep the pipe (|) after "description:" and indent every line by two
# spaces. Quotes and colons are then safe to use.
# Use <p>...</p> for paragraphs, or <br><br> between them.
# ------------------------------------------------------------

description: |
  <p>First paragraph.</p>
  <p>Second paragraph.</p>

# Prerequisites for attendees, e.g. "Basic knowledge of OpenMP". Leave "" if none.
requirements: ""
---