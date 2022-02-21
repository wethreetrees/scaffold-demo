someVar inside template: {{ someVar }}
{{~ someVar = 12345 ~}}

{{- items = ['bananas', 'apples', 'milk', 'bread'] -}}
{{- scaffold.question name:'name' question:"What's your name?" defaultValue:"{{ system.env 'USERNAME' }}" -}}
{{- scaffold.question name:'list' question:"Pick some items" choices:items isArray:true -}}
{{- scaffold.question name:'sentence' question:"Enter any sentence" defaultValue:"scaffolds are SUPER cool!" -}}
{{- scaffold.question name:'word' question:"What's your favorite word?" defaultValue:"scaffold" -}}
{{- scaffold.question name:'adjective' question:"Enter an adjective" defaultValue:"cool" -}}

# Hello, {{ name }}

Welcome to the demo-template!

You can do all kinds of {{ adjective }} stuff with Scaffold templates!

- List items
{{~ for item in list ~}}
  - {{ item }}
{{~ end ~}}
- String manipulation
  - to upper: {{ word | string.upcase }}
  - to lower: {{ word | string.downcase }}
  - capitilized: {{ word | string.capitalize }}
  - capitilize words: {{ sentence | string.capitalizewords }}
  - comparison:
    - contains: {{ sentence }} {{ sentence | string.contains word ? "contains" : "does not contain" }} {{ word }}
    - ends with: {{ sentence }} {{ sentence | string.ends_with word ? "ends with" : "does not end with" }} {{ word }}
    - starts with: {{ sentence }} {{ sentence | string.starts_with word ? "starts with" : "does not start with" }} {{ word }}
  - remove: {{ sentence | string.remove word }}
  - replace: {{ sentence | string.replace word "banana" }}
