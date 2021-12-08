---
layout: default
---

<h2 style="text-align:center">Online SAT Seminar</h2>
This seminar series came out of the Simons Institute program titled "[Satisfiability: Theory, Practice, and Beyond](https://simons.berkeley.edu/programs/sat2021){:target="_blank"}" held at the University of California, Berkeley, USA from Jan-May, 2021.
Everybody interested in Satisfiability and related areas is welcome.

<!-- <h2 style="text-align:center">Join Our Group</h2>
Join our [group](https://groups.google.com/forum/#!forum/ml_logic_seminar/join){:target="_blank"} in order to be notified about upcoming talks. [Subscribe](https://calendar.google.com/calendar/u/1?cid=aTVqMmp2bDZkcnM1bzNpcmg3cGYwa2FyNGdAZ3JvdXAuY2FsZW5kYXIuZ29vZ2xlLmNvbQ){:target="_blank"} in order to add upcoming talks to your calendar. -->

<h2 style="text-align:center">Upcoming Talks</h2>
<div style="overflow-x:auto;">
    <table id="upcoming">
        <tr>
            <th>Date</th>
            <th>Author Name</th>
            <th>Author Affiliation</th>
            <th>Talk Title/Slides</th>
            <th>More Info</th>
        </tr>
        {%- for item in site.data.upcoming -%}
            {%- for talk in item.talks -%}
                <tr>
                    <td>{{ talk.date }}</td>
                    <td><strong>
                        {%- capture authors -%}
                            {%- for author in item.authors -%}
                                {%- if author.link -%} <a href="{{ author.link }}" target="_blank">{{ author.name }}</a>
                                {%- else -%} {{ author.name }}
                                {%- endif -%}
                                <!-- DELIMITER -->
                            {%- endfor -%}
                        {%- endcapture -%}
                        {{ authors | split: "<!-- DELIMITER -->" | join: ", " }}
                    </strong></td>
                    <td>
                        {%- capture affiliations -%}
                            {%- for author in item.authors -%}
                                {%- for affiliation in author.affiliations -%}
                                    {%- if affiliation.link -%} <a href="{{ affiliation.link }}" target="_blank">{{ affiliation.name }}</a>
                                    {%- else -%} {{ affiliation.name }}
                                    {%- endif -%}
                                    <!-- DELIMITER -->
                                {%- endfor -%}
                            {%- endfor -%}
                        {%- endcapture -%}
                        {{ affiliations | split: "<!-- DELIMITER -->" | uniq | join: ", " }}
                    </td>
                    <td><strong>{{ talk.title }}</strong></td>
                    <td><a href="{{ site.baseurl }}/upcoming.html#{{ item.talk-id }}">Link</a></td>
                </tr>
            {%- endfor -%}
        {%- endfor -%}
    </table>
</div>
