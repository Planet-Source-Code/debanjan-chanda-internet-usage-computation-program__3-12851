<div align="center">

## Internet usage computation program


</div>

### Description

An application to check current Internet usage
 
### More Info
 
Using the 'netstat -e' dos command within a C program to compute the internet usage in megabyte :-)


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Debanjan Chanda](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/debanjan-chanda.md)
**Level**          |Intermediate
**User Rating**    |4.0 (8 globes from 2 users)
**Compatibility**  |C, C\+\+ \(general\), Microsoft Visual C\+\+, Borland C\+\+
**Category**       |[Internet/ Browsers/ HTML](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/internet-browsers-html__3-9.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/debanjan-chanda-internet-usage-computation-program__3-12851/archive/master.zip)

### API Declarations

&lt;stdio.h&gt; & &lt;stdlib.h&gt;


### Source Code

```
//////////////////////////////////////////////////
#include <stdio.h>
#include <stdlib.h>
//////////////////////////////////////////////////
int main(void)
{
	unsigned long bytes_sent, bytes_received; /*You can use unsigned long long */
	FILE *temp_file;
	system("netstat -e > usage.in");  /* Sending Output to a temporary File */
	temp_file = fopen("usage.in","r");
	fscanf(temp_file,"%*s%*s%*s%*s%*s%llu%llu",&bytes_received, &bytes_sent);
	printf("%s","Your net usage statistics:(This Session)\n");
	printf("%s","------------------------------------------\n\n");
	printf("%s%8.3f MB\n","Sent:   ", (((double)bytes_sent) / ((double)(1024 * 1024))));
	printf("%s%8.3f MB\n","Received: ", (((double)bytes_received) / ((double)(1024 * 1024))));
	printf("%s%8.3f MB\n\n","Total:  ", (((double)(bytes_sent + bytes_received)) / ((double)(1024 * 1024))));
  system("pause");
  fclose(temp_file);
  system("del usage.in");  /* Deleting the temporary File */
	return 0;
}
//////////////////////////////////////////////////
```

