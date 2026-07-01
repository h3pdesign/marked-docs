# <%= @title %>

<%= @faq_intro %>

<% @faq_items.each tun |item| %>
## <%= item['question'] %>

<%= item['body'] %>

<% Ende %>