// This rule will be triggered if the string javon  is found exactly six times and the string 466 is found  more than ten

rule Count
{
    strings:
        $a = "javon"
        $b = "cs466"

    condition:
        #a == 6 and #b > 10
}
