# <%= @title %>

<%= @faq_intro %>

<% @faq_items.each doe |item| %>
## <%= item['question'] %>

<%= item['body'] %>

<% einde %>