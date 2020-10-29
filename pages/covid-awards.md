---
title: COVID-19 Awards
permalink: /covid-awards/
layout: secondary
---
<section class="usa-section">
<div class="usa-content utility-content usa-grid">
<div class="usa-width-one-whole">

<h1>COVID-19 Awards</h1>

<p class="text-medium" markdown="1">
These awards are related to work concerning COVID-19.
</p>

</div>
</div>
</section>

 <ul class="table monospace">
              <li class="table-row table-header">
                <div class="table-row-item subhead">Company</div>
                <div class="table-row-item subhead">Location</div>
                <div class="table-row-item subhead narrow numeric">Award amount</div>
                <div class="table-row-item subhead narrow numeric">Award date</div>
              </li>
              <div>
              {% for matching in matching_awards %}
                <li class="table-row">
                  <div class="table-row-item" data-header="Company">
                    {% assign awardeeSlug = matching.awardeeName | slugify %}
                    <a href="{{ page.details_url | append: awardeeSlug | relative_url }}" alt="{{ matching.awardeeName }}">
                    <span>{{ matching.awardeeName }}</span>
                    </a>
                  </div>
                  <div class="table-row-item" data-header="Location">{{ matching.awardeeStateCode }}</div>
                  <div class="table-row-item narrow numeric font-mono text-small" data-header="Award amount">{{ matching.fundsObligatedAmt | intcomma_dollar }}</div>
                  <div class="table-row-item narrow numeric font-mono text-small" data-header="Award date">{{ matching.date }}</div>
                </li>
              {% endfor %}
              </div>
            </ul>