// Rule will be triggered if text string is present 

rule TextString
{
    strings:
        $text_string = "xX_not_a_virus_Xx"

    condition:
       $text_string
}
