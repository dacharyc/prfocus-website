{{ with .Title }}# {{ . }}{{ end }}
{{ with .Description }}
> {{ . }}
{{ end }}
{{ .RawContent }}
{{ if .Pages }}## Pages
{{ range .Pages }}{{ if not .Draft }}
- [{{ .Title }}]({{ .Permalink }}index.md){{ with .Description }}: {{ . }}{{ end }}
{{ end }}{{ end }}{{ end }}
