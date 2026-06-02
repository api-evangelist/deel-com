---
title: "[URGENT] POST /rest/v2/contracts returns 403 TOKEN_TYPE_NOT_ALLOWED with personal API token (contracts:write)"
url: "https://stack.deel.com/t/urgent-post-rest-v2-contracts-returns-403-token-type-not-allowed-with-personal-api-token-contracts-write/532#post_1"
date: "2026-06-01"
author: "@tundx0 Olatunde Adegboyebo"
feed_url: "https://stack.deel.com/posts.rss"
---
Summary When we create a contractor contract via POST /rest/v2/contracts using a personal API token with contracts:write (and related scopes), Deel responds with HTTP 403 and error code TOKEN_TYPE_NOT_ALLOWED / message “Invalid token type for this endpoint” . The personal API token has the correct scopes enabled. Example Request POST https://api.letsdeel.com/rest/v2/contracts Content-Type: application/json Accept: application/json Authorization: Bearer Body – { "data": { "title": " ", "country_code": "US", "state_code": " ", "scope_of_work": "As described", "special_clause": "", "client": { "l
