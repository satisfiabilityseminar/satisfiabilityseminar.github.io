---
layout: default
---

<h2 style="text-align:center">Online SAT Seminar</h2>
This seminar series came out of the Simons Institute program [Satisfiability: Theory, Practice, and Beyond](https://simons.berkeley.edu/programs/sat2021){:target="_blank"}. Everybody interested in Satisfiability and related areas is welcome.

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
        {% for item in site.data.upcoming %}
        <tr>
            <td>{{ item.date }}</td>
            <td><strong><a href="{{ item.author-link }}" target="_blank">{{ item.author }}</a></strong></td>
            <td><a href="{{ item.affiliation-link }}" target="_blank">{{ item.affiliation }}</a></td>
            <td><strong>{{ item.title }}</strong></td>
            <td><a href="{{ site.baseurl }}/upcoming.html#{{ item.author }}">Link</a></td>
        </tr>
        {% endfor %}
    </table>
</div>
