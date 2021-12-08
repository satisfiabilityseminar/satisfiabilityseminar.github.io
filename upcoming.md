---
layout: default
---

<h2 style="text-align:center"> Upcoming Talks </h2>
Join our [group](https://groups.google.com/forum/#!forum/ml_logic_seminar/join 
){:target="_blank"} in order to receive emails with the link for the talks.

<div class="talks">
    {% for item in site.data.upcoming %}
    <div class="talk" id="{{ item.author }}">
        <div class="speakerInfo">
            {% capture author-info %}
            ![{{ item.author }}]({{ item.author-img }})
            [{{ item.author }}]({{ item.author-link }}){:target="_blank"}
            [{{ item.affiliation }}]({{ item.affiliation-link }}){:target="_blank"}
            {% endcapture %}
            {{ author-info | strip | markdownify }}
        </div>
        <div class="talkInfo"> 
            <strong> Date:       </strong> {{ item.date }}     <br>
            <strong> Talk Title: </strong> {{ item.title }}    <br>
            <strong> Abstract:   </strong> {{ item.abstract }} <br>
            <strong> Bio:        </strong> {{ item.bio }}
        </div>
    </div>
    {% endfor %}
</div>
