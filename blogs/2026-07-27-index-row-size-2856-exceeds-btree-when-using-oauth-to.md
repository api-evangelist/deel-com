---
title: "Index row size 2856 exceeds btree when using OAuth to connect to MCP server"
url: "https://stack.deel.com/t/index-row-size-2856-exceeds-btree-when-using-oauth-to-connect-to-mcp-server/538#post_1"
date: "2026-07-27"
author: "@Krzysztof Cislo"
feed_url: "https://stack.deel.com/posts.rss"
---
Org name: Doxy.me Details: We’re integrating with Deel’s MCP server ( https://api.letsdeel.com/mcp ) via OAuth. Discovery, dynamic client registration, and user authorization all succeed. The failure happens only at the token exchange step: Request : POST https://api.letsdeel.com/oauth/tokens Auth : public client ( token_endpoint_auth_method: none ) with PKCE Response : 401 unauthorized_client Error message: index row size 2856 exceeds btree version 4 maximum 2704 for index "oauth_access_tokens_token_key" Example request id (x-request-id header): 992c1457ef8744e205ee88fbedcb7526 Time (UTC): 20
