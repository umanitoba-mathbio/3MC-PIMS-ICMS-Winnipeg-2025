---
title: People
layout: page
---

<h2>Instructors</h2>
<div>
    <table>
    {% for person in site.people %}
        {% if person.position_in_school contains "Instructor" %}
                <tr>
                    <td>
                        <div class="column is-one-fifth-desktop is-one-fifth-fullhd is-one-quarter-tablet">
                            <figure class="image is-64x64">
                                {% if person.photo %}
                                    <img class="is-rounded" src="{{site.url}}{{site.baseurl}}{{person.photo}}" alt="{{ person.name }}">
                                {% endif %}
                            </figure>
                        </div>
                    </td>
                    <td>
                        <h2>
                            <a href="{{ site.baseurl }}{{ person.url }}">
                                {{ person.name }}
                            </a>
                        </h2>
                        {{ person.position }} 
                        <br>
                        {{ person.university }}
                        <br>
                        <a href="mailto:{{ person.email }}">{{ person.email }}</a>
                        <br>
                        {% if person.research %}
                                Research interests : {{ person.research }}
                                <br>
                        {% endif %}
                    </td>
                </tr>
        {% endif %}
    {% endfor %}
    </table>
</div>

<h2>Organisation</h2>
<div>
    <table>
    {% for person in site.people %}
        {% if person.position_in_school contains "Organiser" %}
                <tr>
                    <td>
                        <div class="column is-one-fifth-desktop is-one-fifth-fullhd is-one-quarter-tablet">
                            <figure class="image is-64x64">
                    {% if person.photo %}
                                    <img class="is-rounded" src="{{site.url}}{{site.baseurl}}{{person.photo}}" alt="{{ person.name }}">
                    {% endif %}
                            </figure>
                        </div>
                    </td>
                    <td>
                        <h2>
                            {% if person.website %}
                                <a href="{{ person.website }}">
                                    {{ person.name }}
                                </a>
                            {% else %}
                                {{ person.name }}
                            {% endif %}
                        </h2>
                        {{ person.position }} 
                        <br>
                        {{ person.university }}
                        <br>
                        <a href="mailto:{{ person.email }}">{{ person.email }}</a>
                        <br>
                        {{ person.content | markdownify }}
                    </td>
                </tr>
        {% endif %}
    {% endfor %}
    </table>
</div>

