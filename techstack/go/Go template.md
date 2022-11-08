#go #http #network 

[[Go]] templates – in the way we're using them here – are essentially just named text blocks surrounded by `{{define}}` and `{{end}}` tags. [[Template]]s can be embedded into each other using the `{{template}}` tag, like we do above where the `layout` template embeds both the `title` and `body` templates.

#### Example
```go
{{define "layout"}}
	<!doctype html>
	<html>
	<head>
		<meta charset="utf-8">
		<title>{{template "title"}}</title>
		<link rel="stylesheet" href="/static/stylesheets/main.css">
	</head>
	<body>
		{{template "body"}}
		<footer>Made with Go</footer>
	</body>
	</html>
{{end}}
```
