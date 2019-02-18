---
# Featured tags need to have the `list` layout.
layout: page

# The title of the tag's page.
title: Archive

# (Optional) Write a short (~150 characters) description of this featured tag.
description: >
  This is a featured category, which have their own page.

# Setting `menu` will generate an entry in the sidebar for this tag.
menu: true
order: 10
---


<div class="layout--archive js-all">
  {%- include tags.html -%}
  <div class="js-result layout--archive__result d-none">
    {%- include article-list.html articles=site.posts type='brief' show_info=true reverse=true group_by='year' -%}
  </div>
</div>

<script>
  {%- include scripts/archieve.js -%}
</script>

{{ content }}
