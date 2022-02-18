{{- question name:'name' question:"What's your name?" defaultValue:"{{ system.env 'USERNAME' }}" -}}

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
