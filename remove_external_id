#!/bin/bash

website="nesi.zendesk.com"

echo "This script requires that you have a so-called default password for Zendesk"
echo "(i.e., a different password than your single sign-on password through Tuakiri)."
echo "If you do not have such a password or have forgotten it, please visit:"
echo ""
echo "      https://${website}/access/help"
echo ""
echo "To remove an external ID from a user's Zendesk profile, you will need to know"
echo "the user's Zendesk numeric ID. You can find the ID by opening the user's"
echo "Zendesk profile page, and looking in the location bar. The page will display"
echo "as a URL of the following kind:"
echo ""
echo "      https://${website}/agent/users/<numeric_ID>[/...]"
echo ""
echo -n "Please enter the user's Zendesk numeric ID: "
read zdtargetuserid

echo -n "Please enter your Zendesk primary email address: "
read zdmyusername

echo -n "Please enter your Zendesk default password: "
read -s zdmypassword

curl -v \
       	-u "${zdmyusername}:${zdmypassword}" \
	https://${website}/api/v2/users/${zdtargetuserid}.json \
	-H "Content-Type: application/json" \
	-X PUT \
	-d '{"user": {"external_id": ""}}'
echo ""
