// This rule will be triggered if the filesize if over 8 kb

rule FileSize
{
    condition:
       filesize > 8KB
}
