---
layout: default
---

<h2 style="text-align:center"> Upcoming Talks </h2>
Join our [group](https://groups.google.com/forum/#!forum/ml_logic_seminar/join 
){:target="_blank"} in order to receive emails with the link for the talks.

<div class="talks">
    {% for item in site.data.upcoming %}
    <div class="talk" id="{{ item.talk-id }}">
        <div class="speakerInfo"> 
        {% for author in item.authors %}
            <img alt="{{ author.name }}" src="{{ author.img }}"><br>
            {%- if author.link -%}
                <a href="{{ author.link }}" target="_blank">{{ author.name }}</a>
            {%- else -%}
                {{ author.name }}
            {%- endif -%}
            <br>
            {% capture aff %}
            {%- for affiliation in author.affiliations -%}
                {%- if affiliation.link -%}
                    <a href="{{ affiliation.link }}" target="_blank">{{ affiliation.name }}</a>
                {%- else -%}
                    {{ affiliation.name }}
                {%- endif -%}
                <!-- DELIMITER -->
            {%- endfor -%}
            {% endcapture %}
            {{ aff | split: "<!-- DELIMITER -->" | join: ", " }}
            <br>
        {% endfor %}
        </div>
        <div class="talkInfo">
            {%- for talk in item.talks -%}
                {%- if talk.video -%}
                    <iframe width="100%" src="{{ talk.video }}" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                <br>
                {%- endif -%}
                <strong> Date: </strong> {{ talk.date }} <br>
                <strong> Talk Title: </strong> {{ talk.title }} <br>
                {%- if talk.abstract -%} <strong> Abstract: </strong> {{ talk.abstract }} <br> {%- endif -%}
                <hr>
            {%- endfor -%}
            {%- for author in item.authors -%}
                {%- capture bio -%}
                {%- if item.authors.size == 1 -%} **Bio:** {{ author.bio }}
                {%- else -%} **{{ author.name }}'s Bio:** {{ author.bio }} 
                {%- endif -%}
                {%- endcapture -%}
                {{ bio | markdownify }}
                {%- if author.highlights -%}
                    <strong> Highlights: </strong>
                    <ul>
                    {%- for highlight in author.highlights -%}
                        <li>{{ highlight.note }}</li>
                    {%- endfor -%}
                    </ul>
                {%- endif -%}
            {%- endfor -%}
        </div>
    </div>
    {% endfor %}
</div>
