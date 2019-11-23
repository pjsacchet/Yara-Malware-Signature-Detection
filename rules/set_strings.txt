// Rule will be triggered if three of the four possible strings are present in the binary

rule SetStrings
{
    strings:
        $a = "cs466"
        $b = "is"
        $c = "awesome"
        $d = "not"

    condition:
        3 of ($a,$b,$c, $d)
}
