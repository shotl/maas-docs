## Get legal documents

!!! api "Related endpoint"
[GET /v1/legal-docs](https://app.swaggerhub.com/apis-docs/Shotl-transportation/maas/1.0.0-draft#/Docs/getLegalDocs)

Returns a list of legal document URLs in the categories `acknowledgements`, `imprint`, `legal`, `privacy`, `terms`.

## Get a particular legal document

!!! api "Related endpoint"
[GET /v1/legal-docs/{type}](https://app.swaggerhub.com/apis-docs/Shotl-transportation/maas/1.0.0-draft#/Docs/getLegalDoc)

It returns different legal documents specified by the `type` parameter. The returned element is an HTML document in 
string format. Example of imprint legal document returned

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<html>

<head>
	<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
	<meta http-equiv="Content-Style-Type" content="text/css">
	<title>Shotl legal documents</title>
</head>

<body>
	<p>&nbsp;</p>
	<p>imprint</p>
</body>

</html>
```