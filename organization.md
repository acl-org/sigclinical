---
layout: default
title: Organization
order: 2
---

<div class="accordion" id="boards">
  {% for board in site.data.boards -%}
  <div class="accordion-item">
    <h2 class="accordion-header" id="heading{{ forloop.index }}">
      <button class="accordion-button" type="button" data-bs-toggle="collapse" data-bs-target="#collapse{{ forloop.index }}" aria-expanded="{% if forloop.index == 1 %}true{% else %}false{% endif %}" aria-controls="collapse{{ forloop.index }}">
         {{ board.year }} SIGClinical Board
      </button>
    </h2>
    <div id="collapse{{ forloop.index }}" class="accordion-collapse collapse{% if forloop.index == 1 %} show{% endif %}" aria-labelledby="heading{{ forloop.index }}" data-bs-parent="#boards">
      <div class="accordion-body">
        {% for group in board.groups -%}
        {{ group.title }}
        <ul>
          {% for member in group.members -%}
          <li><strong>{{ member.title }}</strong>: {{ member.name }}, {{ member.affiliation }}, {{ member.term }}</li>
          {% endfor -%}
        </ul>
        {% endfor -%}
      </div>
    </div>
  </div>
  {% endfor -%}
</div>
