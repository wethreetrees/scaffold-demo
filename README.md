{{- question name:'name' question:"What's your name?" defaultValue:"{{ system.env 'USERNAME' }}" -}}
{{- question name:'list' question:"Pick some items" choices:['bananas', 'apples', 'milk', 'bread'] isArray:true -}}
{{- question name:'sentence' question:"Enter any sentence" defaultValue:"scaffolds are SUPER cool!" -}}
{{- question name:'word' question:"What's your favorite word?" defaultValue:"scaffold" -}}
{{- question name:'adjective' question:"Enter an adjective" defaultValue:"cool" -}}

# Hello, {{ name }}

Welcome to the demo-template!

You can do all kinds of {{ adjective }} stuff with Scaffold templates!

- List items
{{ for item in list }}
  - {{ item }}
{{ end }}
- String manipulation
  - to upper: {{ word | string.upcase }}
  - to lower: {{ word | string.downcase }}
  - capitilized: {{ word | string.capitalize }}
  - capitilize words: {{ sentence | string.capitalizewords }}
  - comparison:
    - contains: {{ sentence | string.contains word }}
    - ends with: {{ sentence | string.ends_with word }}
    - starts with: {{ sentence | string.starts_with word }}
  - remove: {{ sentence | string.remove word }}
  - replace: {{ sentence | string.replace word "banana" }}
