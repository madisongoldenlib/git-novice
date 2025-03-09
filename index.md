---
layout: workshop      # DON'T CHANGE THIS.
# More detailed instructions (including how to fill these variables for an
# online workshop) are available at
# https://carpentries.github.io/workshop-template/customization/index.html
venue: "University of Utah"        # brief name of the institution that hosts the workshop without address (e.g., "Euphoric State University")
address: "Marriott Library, Digital Matters: Room 2751"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria"), videoconferencing URL, or 'online'
country: "us"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes) for the institution that hosts the workshop
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) for the workshop
latitude: "40.768610"        # decimal latitude of workshop venue (use https://www.latlong.net/)
longitude: "-111.833840"       # decimal longitude of the workshop venue (use https://www.latlong.net)
humandate: "April 9 2025"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "9:00 am - 12:30 pm MDT"    # human-readable times for the workshop e.g., "9:00 am - 4:30 pm CEST (7:00 am - 2:30 pm UTC)"
startdate: 2025-04-09      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2025-04-09       # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Madison Golden"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["Kaylee Alexander"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["madison.golden@utah.edu", "andrew.george@hsc.utah.edu"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes: TBD # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document (e.g., https://pad.carpentries.org/2015-01-01-euphoria)
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %} HEADER

Edit the values in the block above to be appropriate for your workshop. If the value is not 'true', 'false', 'null', or a number, please use double quotation marks around the value, unless specified otherwise. And run 'make workshop-check' before committing to make sure that changes are good. {% endcomment %}

{% comment %} 8< ============= For a workshop delete from here ============= For a workshop please delete the following block until the next dashed-line {% endcomment %}

{% comment %} 8< ============================= until here ================== {% endcomment %}

<strong>Registration: Use [THIS LINK](https://t.e2ma.net/click/r535aj/r5f3k6cd/7p69gq) to sign up for this workshop</strong>

<h3>General Information</h3>
{% comment %} INTRODUCTION

Edit the general explanatory paragraph below if you want to change the pitch. {% endcomment %} {% if site.carpentry == "swc" %} {% include swc/intro.html %} {% elsif site.carpentry == "dc" %} {% include dc/intro.html %} {% elsif site.carpentry == "lc" %} {% include lc/intro.html %} {% endif %}

{% if site.pilot %} This is a pilot workshop, testing out a lesson that is still under development. The lesson authors would appreciate any feedback you can give them about the lesson content and suggestions for how it could be further improved. {% endif %}

{% comment %} AUDIENCE

Explain who your audience is. (In particular, tell readers if the workshop is only open to people from a particular institution. {% endcomment %} {% if site.carpentry == "swc" %} {% include swc/who.html %} {% elsif site.carpentry == "dc" %} {% include dc/who.html %} {% elsif site.carpentry == "lc" %} {% include lc/who.html %} {% endif %}

{% comment %} LOCATION

This block displays the address and links to maps showing directions if the latitude and longitude of the workshop have been set. You can use https://www.latlong.net/ to find the lat/long of an address. {% endcomment %} {% assign begin_address = page.address | slice: 0, 4 | downcase %} {% if page.address == "online" %} {% assign online = "true_private" %} {% elsif begin_address contains "http" %} {% assign online = "true_public" %} {% else %} {% assign online = "false" %} {% endif %} {% if page.latitude and page.longitude and online == "false" %}

<strong>Where:</strong> {{page.address}}.

{% elsif online == "true_public" %}
Where: online at {{page.address}}. If you need a password or other information to access the training, the instructor will pass it on to you before the workshop.

{% elsif online == "true_private" %}
Where: This training will take place online. The instructors will provide you with the information you will need to connect to this meeting.

{% endif %}
{% comment %} DATE

This block displays the date and links to Google Calendar. {% endcomment %} {% if page.humandate %}

<strong>When:</strong> {{page.humandate}}. {% include workshop_calendar.html %}

{% endif %}
{% comment %} SPECIAL REQUIREMENTS

Modify the block below if there are any special requirements. {% endcomment %}

<strong>Requirements:</strong> {% if online == "false" %} Participants must bring a laptop on which you have admin privileges since you will need to be able to install git on your laptop to participate in the workshop. {% else %} Participants must have access to a computer with a Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges on. {% endif %}

{% comment %} ACCESSIBILITY

Modify the block below if there are any barriers to accessibility or special instructions. {% endcomment %}

<strong>Accessibility:</strong> We are dedicated to providing a positive and accessible learning environment for all. Please notify the instructors in advance of the workshop if you require any accommodations or if there is anything we can do to make this workshop more accessible to you.


{% comment %} CONTACT EMAIL ADDRESS

Display the contact email address set in the configuration file. {% endcomment %}

<strong>Contact:</strong> Please email {% if page.email %} {% for email in page.email %} {% if forloop.last and page.email.size > 1 %} or {% else %} {% unless forloop.first %} , {% endunless %} {% endif %} {{email}} {% endfor %} {% else %} to-be-announced {% endif %} for more information.

{% comment %} WHO CAN ATTEND?

If you would like to specify who can attend the workshop, you can use the section below.

Move the 'endcomment' tag above the beginning of the following

tag to make this section visible.

Edit the text to match who can attend the workshop. For instance:

This workshop is open to affiliates to ABC university.
This workshop is open to the public.
If you are interested in attending this workshop, contact me@example.com for more information
Who can attend?: This workshop is open to ....

{% endcomment %}
{% comment%} CODE OF CONDUCT {% endcomment %}

<strong>Code of Conduct:</strong> Everyone who participates in Carpentries activities is required to conform to the Code of Conduct. This document also outlines how to report an incident if needed.

[Report a Code of Conduct Incident](https://goo.gl/forms/KoUfO53Za3apOuOK2)

<p><strong>Setup:</strong> Participants must bring a laptop on which you have admin privileges since you will need to be able to install git on your laptop to participate in the workshop. We recommend that you try to get set up before the workshop by downloading and installing git.<br>
Mac: Install git from the git website.<br>
Windows: Install git for windows, which will also install a "git bash" application that we will use as a terminal.<br></p>
[Create a free GitHub account.](https://docs.github.com/en/get-started/start-your-journey/creating-an-account-on-github)

{% comment %} SCHEDULE

Show the workshop's schedule.

Small changes to the schedule can be made by modifying the schedule.html found in the _includes folder for your workshop type (swc, lc, or dc). Edit the items and times in the table to match your plans. You may also want to change 'Day 1' and 'Day 2' to be actual dates or days of the week.

For larger changes, a blank template for a 4-day workshop (useful for online teaching for instance) can be found in _includes/custom-schedule.html. Add the times, and what you will be teaching to this file. You may also want to add rows to the table if you wish to break down the schedule further. To use this custom schedule here, replace the block of code below the Schedule <h2> header below with {% include custom-schedule.html %}. {% endcomment %}

{% if site.carpentry == "swc" %} {% include swc/schedule.html %} {% elsif site.carpentry == "dc" %} {% include dc/schedule.html %} {% elsif site.carpentry == "lc" %} {% include lc/schedule.html %} {% elsif site.carpentry == "incubator" %} This workshop is teaching a lesson in The Carpentries Incubator. Please check [the lesson homepage]({{ site.incubator_lesson_site }}) for a list of lesson sections and estimated timings. {% endif %}

{% comment %} Edit/replace the text above if you want to include a schedule table. See the contents of the _includes/custom-schedule.html file for an example of how one of these schedule tables is constructed. {% endcomment %}

{% if site.pilot %} The lesson taught in this workshop is being piloted and a precise schedule is yet to be established. The workshop will include regular breaks. Please contact the workshop organisers if you would like more information about the planned schedule. {% endif %}
