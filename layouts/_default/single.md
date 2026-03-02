{{ with .Title }}# {{ . }}{{ end }}
{{ with .Date }}*{{ .Format "January 2, 2006" }}*{{ end }}

{{ .RawContent }}
