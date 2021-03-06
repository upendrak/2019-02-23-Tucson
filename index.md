---
layout: workshop      # DON'T CHANGE THIS.
carpentry: "swc"    # what kind of Carpentry (must be either "lc" or "dc" or "swc")
venue: "Learn Data Wrangling at the University of Arizona!"        # brief name of host site without address (e.g., "Euphoric State University")
address: "Please check your email for the workshop location!"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "us"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/ISO_639-1)
latlng: "32.231901,-110.9495000"       # decimal latitude and longitude of workshop venue (e.g., "41.7901128,-87.6007318" - use https://www.latlong.net/)
humandate: "Feb. 23-24, 2019"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "8:30-17:00"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2019-02-23      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2019-02-24        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["t.b.a."] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["t.b.a."]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["hilgert@bio5.org"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes: https://pad.carpentries.org/2019-02-23-Tucson # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %}
  HEADER

  Edit the values in the block above to be appropriate for your workshop.
  If the value is not 'true', 'false', 'null', or a number, please use
  double quotation marks around the value, unless specified otherwise.
  And run 'make workshop-check' *before* committing to make sure that changes are good.
{% endcomment %}

{% comment %}
  EVENTBRITE

  This block includes the Eventbrite registration widget if
  'eventbrite' has been set in the header.  You can delete it if you
  are not using Eventbrite, or leave it in, since it will not be
  displayed if the 'eventbrite' field in the header is not set.
{% endcomment %}
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="280px"
  scrolling="auto">
</iframe>
{% endif %}

<h2 id="general">General Information</h2>

<p>
<br><center><strong><h3>This workshop is taking place during the annual
<a href="http://www.tucsonrodeo.com/" target="blank">Rodeo Week</a> in Tucson, AZ.</h3>
<h3>Come for the rodeo, stay to wrangle some data!</h3></strong></center><br>
</p>
<p><h4><center><strong>Apply for the workshop at <a href="https://goo.gl/PA9SSp" target='blank'>https://goo.gl/PA9SSp</a>.</strong></center></h4><br> </p>

{% comment %}
  INTRODUCTION

  Edit the general explanatory paragraph below if you want to change
  the pitch.
{% endcomment %}
{% if page.carpentry == "swc" %}
  {% include sc/intro.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/intro.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/intro.html %}
{% endif %}

{% comment %}
  AUDIENCE

  Explain who your audience is.  (In particular, tell readers if the
  workshop is only open to people from a particular institution.
{% endcomment %}
{% if page.carpentry == "swc" %}
  {% include sc/who.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/who.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/who.html %}
{% endif %}

{% comment %}
  LOCATION

  This block displays the address and links to maps showing directions
  if the latitude and longitude of the workshop have been set.  You
  can use https://itouchmap.com/latlong.html to find the lat/long of an
  address.
{% endcomment %}
{% if page.latlng %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latlng}}">Google Maps</a>.
</p>
{% endif %}

{% comment %}
  DATE

  This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
  SPECIAL REQUIREMENTS

  Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong> Participants must bring a laptop with a
  Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges
  on. They should have a few specific software packages installed (listed
  <a href="#setup">below</a>). They are also required to abide by
  {% if page.carpentry == "swc" %}
  Software Carpentry's
  {% elsif page.carpentry == "dc" %}
  Data Carpentry's
  {% elsif page.carpentry == "lc" %}
  Library Carpentry's
  {% endif %}
  <a href="{{site.swc_site}}/conduct.html">Code of Conduct</a>.
</p>

{% comment %}
  ACCESSIBILITY

  Modify the block below if there are any barriers to accessibility or
  special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this workshop
  accessible to everybody.
  The workshop organizers have checked that:
</p>
<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>
<!--<p>
  Materials will be provided in advance of the workshop and
  large-print handouts are available if needed by notifying the
  organizers in advance.  If we can help making learning easier for
  you (e.g. sign-language interpreters, lactation facilities) please
  get in touch (using contact details below) and we will
  attempt to provide them.
</p>-->
<p>
  Links to workshop materials are being provided below. If we can provide additional resources to help making learning easier for you (e.g. large-font hand-outs, sign-language interpreters, lactation facilities) please get in touch (using contact details below) and we will attempt to provide them.
</p>

{% comment %}
  CONTACT EMAIL ADDRESS

  Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact</strong>:
  Please email the workshop administrator at
  {% if page.email %}
    {% for email in page.email %}
      {% if forloop.last and page.email.size > 1 %}
        or
      {% else %}
        {% unless forloop.first %}
        ,
        {% endunless %}
      {% endif %}
      <a href='mailto:{{email}}'>{{email}}</a>
    {% endfor %}
  {% else %}
    to-be-announced
  {% endif %}
  for more information.
</p>

<hr/>

{% comment %} 
 SURVEYS - DO NOT EDIT SURVEY LINKS 
{% endcomment %}
<h2 id="surveys">Surveys</h2>
<p>Please be sure to complete these surveys before and after the workshop.</p>
{% if site.carpentry == "swc" %} 
<p><a href="{{ site.swc_pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.swc_post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% elsif site.carpentry == "dc" %}
<p><a href="{{ site.dc_pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.dc_post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% elsif site.carpentry == "lc" %}
<p><a href="{{ site.lc_pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.lc_post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% endif %}

<hr/>


{% comment %}
  SCHEDULE

  Show the workshop's schedule.  Edit the items and times in the table
  to match your plans.  You may also want to change 'Day 1' and 'Day
  2' to be actual dates or days of the week.
{% endcomment %}
<h2 id="schedule">Schedule</h2>

<div class="row">
  <div class="col-md-6">
    <h3>Saturday February 23</h3>
    <table class="table table-striped">
      <tr> <td>08:30</td> <td><a href="http://swcarpentry.github.io/shell-novice/" target="_blank">Access and navigate the command line / Bash Shell</a></td> </tr>
      <tr> <td>10:30</td> <td>Break</td> </tr>
      <tr> <td>10:45</td> <td> <a href="http://swcarpentry.github.io/git-novice/" target="_blank">Manage data with git/GitHub</a></td> </tr>
      <tr> <td>12:00</td> <td>Break</td> </tr>
      <tr> <td>13:00</td> <td><a href="http://swcarpentry.github.io/shell-novice/" target="_blank">Automate tasks with shell scripts</a></td> </tr>
      <tr> <td>14:45</td> <td>Break</td> </tr>
      <tr> <td>15:00</td> <td><a href="http://swcarpentry.github.io/git-novice/" target="_blank">Share data and scripts/programs with git/GitHub</a></td> </tr>
      <tr> <td>17:00</td> <td>End of Day</td> </tr>
    </table>
  </div>
  <div class="col-md-6">
    <h3>Sunday February 24</h3>
    <table class="table table-striped">
      <tr> <td>08:30</td>  <td><a href="http://swcarpentry.github.io/python-novice-gapminder/" target="_blank">Analyze scientific data with Python </a> and <a href="http://swcarpentry.github.io/git-novice/" target="_blank">git/GitHub</a></td> </tr>
      <tr> <td>10:30</td>  <td>Break</td> </tr>
      <tr> <td>11:00</td>  <td><a href="http://swcarpentry.github.io/python-novice-gapminder/" target="_blank">Analyze scientific data with Python </a> and <a href="http://swcarpentry.github.io/git-novice/" target="_blank">git/GitHub</a>, cont.</td> </tr>
      <tr> <td>12:00</td>  <td>Break</td> </tr>
      <tr> <td>13:00</td>  <td><a href="http://swcarpentry.github.io/python-novice-gapminder/" target="_blank">Analyze scientific data with Python </a> and <a href="http://swcarpentry.github.io/git-novice/" target="_blank">git/GitHub</a>, cont.</td> </tr>
      <tr> <td>14:45</td>  <td>Break</td> </tr>
      <tr> <td>15:00</td>  <td><a href="http://swcarpentry.github.io/python-novice-gapminder/" target="_blank">Analyze scientific data with Python </a> and <a href="http://swcarpentry.github.io/git-novice/" target="_blank">git/GitHub</a>, cont.</td> </tr>
      <tr> <td>17:00</td>  <td>End of Day</td> </tr>
    </table>
  </div>
</div>

<p>Schedule subject to change if necessary.</p>

<hr/>

<h2 id="collaboration">Online Collaboration</h2>

{% comment %}
  Collaborative Notes

  If you want to use an Etherpad, go to

      http://pad.software-carpentry.org/YYYY-MM-DD-site

  where 'YYYY-MM-DD-site' is the identifier for your workshop,
  e.g., '2015-06-10-esu'.
{% endcomment %}
{% if page.collaborative_notes %}
<p id="collaborative_notes">
  We will use the collaborative document at <a href="{{page.collaborative_notes}}">{{page.collaborative_notes}}</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
{% endif %}

<hr/>

{% comment %}
  SYLLABUS

  Show what topics will be covered.

  1. If your workshop is R rather than Python, remove the comment
     around that section and put a comment around the Python section.
  2. Some workshops will delete SQL.
  3. Please make sure the list of topics is synchronized with what you
     intend to teach.
  4. You may need to move the div's with class="col-md-6" around inside
     the div's with class="row" to balance the multi-column layout.

  This is one of the places where people frequently make mistakes, so
  please preview your site before committing, and make sure to run
  'tools/check' as well.
{% endcomment %}
<!-- <h2 id="syllabus">Syllabus</h2> -->

{% if page.carpentry == "swc" %}
  {% include sc/syllabus.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/syllabus.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/syllabus.html %}
{% endif %}

<hr/>

<h2 id="syllabus">Syllabus & Learning Objectives</h2>

<div class="row">
  <div class="col-md-6">
	  <h3 id="syllabus-shell">Take control with the Bash Shell (Command Line/Shell/Unix)</h3>
    <ul>
	    <li>Work <em>in</em> vs. work <em>below</em> the GUI</li>
	    <li>Navigate the shell</li>
	    <li><code>Find</code>, create, copy, move and delete folders and files</li>
	    <li>Shell over GUI: Command history and tab completion</li>
	    <li>Connect commands into workflows: pipes and redirection</li>
	    <li>Automate repetitive tasks: loops</li>
	    <li>Save and run workflows in scripts</li>
	  </ul>
	  <u>Resources:</u>
	  <ul>
		  <li><a href="{{site.swc_pages}}/shell-novice">Shell Lessons</a></li>
		  <li><a href="{{site.swc_pages}}/shell-novice/reference.html">Shell Quick Reference</a></li>
		  <li><a href="http://explainshell.com/" target="_blank"><em>Explain Shell</em> (Parses shell commands and shows docs about the command)</a></li>
		  <li><a href="http://www.shellcheck.net/" target="_blank"><em>ShellCheck</em> (Identifies bugs in shell scripts)</a></li>
		  <li><a href="http://man.he.net/" target="_blank"><em>Linux Man Pages Online</em> (Same content as command line man/help pages)</a></li>
	  </ul>
  </div>

  <div class="col-md-6">
	  <h3 id="syllabus-git">Collaborate with git/GitHub</h3>
    <ul>
	    <li>Access a repository and pull files</li>
	    <li>Create a repository</li>
	    <li>Record changes: <code>add</code>, <code>commit</code>, ...</li>
	    <li>View changes: <code>status</code>, <code>diff</code>, ...</li>
	    <li>Ignore files</li>
	    <li>Work on the web: <code>clone</code>, <code>pull</code>, <code>push</code>, ...</li>
	    <li>Resolve conflicts</li>
	  </ul>
	  <u>Resources:</u>
	  <ul>
		  <li><a href="{{site.swc_pages}}/git-novice">Git Lessons</a></li>
		  <li><a href="{{site.swc_pages}}/git-novice/reference/">Git Quick Reference</a></li>
		  <li><a href="https://git-scm.com/book/en/v2/Git-in-Other-Environments-Git-in-Bash" target="_blank"><i>Mac/Linux:</i> Integrating Git into your shell prompt</a></li>
		  <li><a href="https://github.com/magicmonty/bash-git-prompt" target="_blank">An informative and fancy bash prompt for Git users</a></li>
		  <li><a href="https://education.github.com/pack" target="_blank">Unlimited <em>private</em> repositories for free on Github, <i>while you are a student</i></a></li>
		  <li><a href="https://git-annex.branchable.com/" target="_blank">Git for Archiving Data</a></li>
	  </ul>
  </div>

<div class="col-md-6">
    <h3 id="syllabus-python">Analyse scientific data with Python</h3>
    <ul>
      <li>Use libraries</li>
      <li>Work with arrays</li>
      <li>Read and plot data</li>
      <li>Create and use functions</li>
      <li>Use loops and conditionals</li>
      <li>Use Python from the command line</li>
      <li>Defensive programming</li>
    </ul>
	  <u>Resources:</u>
	  <ul>
		  <li><a href="{{site.swc_pages}}/python-novice-gapminder">Python Lessons</a></li>
		  <li><a href="{{site.swc_pages}}/python-novice-gapminder/reference/">Python Quick Reference</a></li>
                  <li><a href="https://www.codecademy.com/learn/python" target="_blank">Codecademy: Interactive Python practice lessons</a></li>
		  <li><a href="http://rosalind.info/problems/list-view/?location=python-village" target="_blank">Rosalind Python Bioinformatics Practice</a></li>
		  <li><a href="https://www.datacamp.com/community/tutorials/tutorial-jupyter-notebook#gs.mz7KeNQ" target="_blank">Jupyter Notebook tutorial</a></li>
		  <li><a href="https://plot.ly/python/" target="_blank">Interactive plotting with Plotly (available for R and for Python)</a></li>


    </ul>
  </div>
</div>
  
<p>Syllabus subject to change if necessary.</p>


<hr/>

{% comment %}
  SETUP

  Delete irrelevant sections from the setup instructions.  Each
  section is inside a 'div' without any classes to make the beginning
  and end easier to find.

  This is the other place where people frequently make mistakes, so
  please preview your site before committing, and make sure to run
  'tools/check' as well.
{% endcomment %}

<h2 id="setup">Prepare Your Computer</h2>

<p>
  To participate in a
  {% if page.carpentry == "swc" %}
  Software Carpentry
  {% elsif page.carpentry == "dc" %}
  Data Carpentry
  {% elsif page.carpentry == "lc" %}
  Library Carpentry
  {% endif %}
  workshop,
  you will need access to the software described below. Unless you prepare your laptop as described below you will be unable to follow along.
  In addition, you will need an up-to-date web browser, we recommend Firefox, Chrome or Safari as Internet Explorer/Edge can be buggy.
</p>
<p>
<em>Should you encounter issues</em> while installing the software below, please look for a solution in our
  <a href = "{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
If even this does not help, please get in touch with us at the contact email listed above and we will attempt to provide a solution.
</p>

<div id="shell"> {% comment %} Start of 'shell' section. {% endcomment %}
  <h3>The Bash Shell</h3>

  <p>
    Bash is a commonly-used shell environment that gives you the power to quickly do simple tasks on your computer. Bash stands for 'Bourne Again Shell'; if you are interested in the history of the term and the underlying technological development, please search the Web for 'Bash Shell'.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="shell-windows">Windows</h4>
      <a href="https://www.youtube.com/watch?v=339AEqk9c-8">Video Tutorial</a>
      <ol>
        <li>Download the Git for Windows <a href="https://git-for-windows.github.io/">installer</a>.</li>
        <li>Run the installer and follow the steps below:
          <ol>
            {% comment %} Git 2.18.0 Setup {% endcomment %}
            <li>
                Click on "Next" four times (two times if you've previously
                installed Git).  You don't need to change anything
                in the Information, location, components, and start menu screens.
            </li>
            <li>
                Ensure “Use the nano editor by default” is selected and click on “Next”.
            </li>
            {% comment %} Adjusting your PATH environment {% endcomment %}
            <li>
                Ensure "Use Git from Git Bash only" is selected and click on "Next".
                If you forget to do this programs that you need for the workshop will not work properly.
                If this happens rerun the installer and select the appropriate option.
            </li>
            {% comment %} Choosing the SSH executable {% endcomment %}
                <li>Ensure "Use the OpenSSL Library" is selected and click on "Next".
            </li>
            {% comment %} Configuring the line ending conversions {% endcomment %}
            <li>
                Ensure "Checkout Windows-style, commit Unix-style line endings" is selected and click on "Next".
            </li>
            {% comment %} Configuring the terminal emulator to use with Git Bash {% endcomment %}
            <li>
                Ensure "Use Windows' default console window" is selected and click on "Next".
            </li>
            {% comment %} Configuring experimental performance tweaks {% endcomment %}
             <li>
                 Ensure "Enable file system caching" and "Enable Git Credential Manager" is selected and click on "Next". 
            </li>
            <li>Click on "Install".</li>
            {% comment %} Installing {% endcomment %}
            {% comment %} Completing the Git Setup Wizard {% endcomment %}
            <li>Click on "Finish".</li>
          </ol>
        </li>
        <li>
          If your "HOME" environment variable is not set (or you don't know what this is):
          <ol>
            <li>Open command prompt (Open Start Menu then type <code>cmd</code> and press [Enter])</li>
            <li>
              Type the following line into the command prompt window exactly as shown:
              <p><code>setx HOME "%USERPROFILE%"</code></p>
            </li>
            <li>Press [Enter], you should see <code>SUCCESS: Specified value was saved.</code></li>
            <li>Quit command prompt by typing <code>exit</code> then pressing [Enter]</li>
          </ol>
        </li>
      </ol>
      <p>This will provide you with both Bash and Git in the Git Bash program.</p>
    </div>
    <div class="col-md-4">
      <h4 id="shell-macosx">macOS</h4>
      <p>
        The default shell in all versions of macOS is Bash, so no
        need to install anything.  You access Bash from the Terminal
        (found in
        <code>/Applications/Utilities</code>).
        See the Git installation <a href="https://www.youtube.com/watch?v=9LQhwETCdwY ">video tutorial</a>
        for an example on how to open the Terminal.
        You may want to keep
        Terminal in your dock for this workshop.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="shell-linux">Linux</h4>
      <p>
        The default shell is usually Bash, but if your
        machine is set up differently you can run it by opening a
        terminal and typing <code>bash</code>.  There is no need to
        install anything.
      </p>
    </div>
  </div>
</div> {% comment %} End of 'shell' section. {% endcomment %}

<div id="editor"> {% comment %} Start of 'editor' section. {% endcomment %}
  <h3>Text Editor</h3>

  <p>
Writing code is much easier with respectively optimized text editors that include features such as automatic color-coding of key words and syntax-highlighting. We will use the basic editor '<strong>nano</strong>' in the workshop; it comes pre-installed with the git-bash download above for Windows, Mac and Linux.
  </p>

<div class="row">
    <div class="col-md-4">
      <h4 id="editor-windows">Windows</h4>
<p>
	Click the Start button and type 'git bash' into the search window.<br> 
	Click on the "Git Bash" icon to open the shell.<br>
	Type 'nano test.txt' to open a text editor. <strong>IF this does not open the nano text editor contact the workshop administrator at the email listed above.</strong><br>
	Type 'Test'.<br>
	To exit the nano editor press Ctrl and type 'x' (a.k.a. '^X'; additional commands are listed at the bottom of the text edito window.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="editor-macosx">macOS</h4>
      <p>
        During the workshop we will be using the basic editor nano. nano should be pre-installed; see the Git installation <a href="https://www.youtube.com/watch?v=9LQhwETCdwY ">video tutorial</a> for an example on how to open nano.        
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="editor-linux">Linux</h4>
      <p>
        During the workshop we will be using the basic editor nano. nano should be pre-installed
      </p>
</div>
</div>
</div> {% comment %} End of 'editor' section. {% endcomment %}


<div id="git"> {% comment %} Start of 'Git' section. GitHub browser compatability
           is given at https://help.github.com/articles/supported-browsers/{% endcomment %}
  <h3>Git</h3>
  <p>
    Git is a version control system that lets you track who made changes
    to what when and has options for easily updating a shared or public
    version of your code
    on <a href="https://github.com/">github.com</a>. You will need a
    <a href="https://help.github.com/articles/supported-browsers/">supported</a>
    web browser (current versions of Chrome, Firefox or Safari,
    or Internet Explorer version 9 or above).
  </p>
  <p>
	  <strong>For the workshop you will need a GitHub account,</strong> if you don't have one already please get it at <a href="https://github.com/">github.com</a>. Basic GitHub accounts are free. However, please consider what personal information you'd like to reveal. For example, you may want to review these <a href="https://help.github.com/articles/keeping-your-email-address-private/">instructions for keeping your email address private</a> at GitHub.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="git-windows">Windows</h4>
      <p>
        Git should be installed on your computer as part of your Bash
        install (described above).
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="git-macosx">macOS</h4>
      <a href="https://www.youtube.com/watch?v=9LQhwETCdwY ">Video Tutorial</a>
      <p>
        <strong>For OS X 10.9 and higher</strong>, install Git for Mac
        by downloading and running the most recent "mavericks" installer from
        <a href="http://sourceforge.net/projects/git-osx-installer/files/">this list</a>.
        Because this installer is not signed by the developer, you may have to
        right click (control click) on the .pkg file, click Open, and click
        Open on the pop up window. 
        After installing Git, there will not be anything in your <code>/Applications</code> folder,
        as Git is a command line program.
        <strong>For older versions of OS X (10.5-10.8)</strong> use the
        most recent available installer labelled "snow-leopard"
        <a href="http://sourceforge.net/projects/git-osx-installer/files/">available here</a>.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="git-linux">Linux</h4>
      <p>
        If Git is not already available on your machine you can try to
        install it via your distro's package manager. For Debian/Ubuntu run
        <code>sudo apt-get install git</code> and for Fedora run
        <code>sudo dnf install git</code>.
      </p>
    </div>
  </div>
</div> {% comment %} End of 'Git' section. {% endcomment %}

<div id="python"> {% comment %} Start of 'Python' section. Remove the third paragraph if
           the workshop will teach Python using something other than
           the Jupyter notebook.
           Details at https://jupyter-notebook.readthedocs.io/en/stable/notebook.html#browser-compatibility {% endcomment %}
  <h3>Python</h3>

  <p>
    <a href="https://python.org">Python</a> is a popular language for
    research computing, and great for general-purpose programming as
    well.  Installing all of its research packages individually can be
    a bit difficult, so we recommend
    <a href="https://www.anaconda.com/distribution/">Anaconda</a>,
    an all-in-one installer.
  </p>

    <p>
      Regardless of how you choose to install it,
      <strong>please make sure you install Python version 3.x</strong>
      (e.g., 3.6 is fine).
    </p>

    <p>
      We will teach Python using the <a href="https://jupyter.org/">Jupyter notebook</a>,
      a programming environment that runs in a web browser. For this to work you will need a reasonably
      up-to-date browser. The current versions of the Chrome, Safari and
      Firefox browsers are all
      <a href="https://jupyter-notebook.readthedocs.io/en/stable/notebook.html#browser-compatibility">supported</a>
      (some older browsers, including Internet Explorer version 9
      and below, are not).
    </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="python-windows">Windows</h4>
      <a href="https://www.youtube.com/watch?v=xxQ0mzZ8UvA">Video Tutorial</a>
      <ol>
        <li>Open <a href="https://www.anaconda.com/download/#windows">https://www.anaconda.com/download/#windows</a> with your web browser.</li>
        <li>Download the Python 3 installer for Windows.</li>
        <li>Install Python 3 using all of the defaults for installation <em>except</em> make sure to check <strong>Make Anaconda the default Python</strong>.</li>
      </ol>
    </div>
    <div class="col-md-4">
      <h4 id="python-macosx">macOS</h4>
      <a href="https://www.youtube.com/watch?v=TcSAln46u9U">Video Tutorial</a>
      <ol>
        <li>Open <a href="https://www.anaconda.com/download/#macos">https://www.anaconda.com/download/#macos</a> with your web browser.</li>
        <li>Download the Python 3 installer for OS X.</li>
        <li>Install Python 3 using all of the defaults for installation.</li>
      </ol>
    </div>
    <div class="col-md-4">
      <h4 id="python-linux">Linux</h4>
      <ol>
        <li>Open <a href="https://www.anaconda.com/download/#linux">https://www.anaconda.com/download/#linux</a> with your web browser.</li>
        <li>Download the Python 3 installer for Linux.<br>
          (The installation requires using the shell. If you aren't
           comfortable doing the installation yourself
           stop here and request help at the workshop.)
        </li>
        <li>
          Open a terminal window.
        </li>
        <li>
          Type <pre>bash Anaconda3-</pre> and then press
          tab. The name of the file you just downloaded should
          appear. If it does not, navigate to the folder where you
          downloaded the file, for example with:
          <pre>cd Downloads</pre>
          Then, try again.
        </li>
        <li>
          Press enter. You will follow the text-only prompts. To move through
          the text, press the space key. Type <code>yes</code> and
          press enter to approve the license. Press enter to approve the
          default location for the files. Type <code>yes</code> and
          press enter to prepend Anaconda to your <code>PATH</code>
          (this makes the Anaconda distribution the default Python).
        </li>
        <li>
          Close the terminal window.
        </li>
      </ol>
    </div>
  </div>
{% comment %}
  <p>
  Once you are done installing the software listed above,
  please go to <a href="setup/index.html">this page</a>,
  which has instructions on how to test that everything was installed correctly.
  </p>
{% endcomment %}

  <p>
  Once you are done installing the software listed above,
  please go to <a href="setup/index.html">this page</a>,
  which has instructions on how to test that everything was installed correctly.
  </p>
</div> {% comment %} End of 'Python' section. {% endcomment %}
