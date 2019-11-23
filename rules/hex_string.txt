// Rule will be triggered if text string or hex string is present 

rule HexString
{
    strings:
        $my_text_string = "some text can be here"
        $my_hex_string = { 74 68 69 73 20 69 73 20 6E 6F 74 20 61 20 76 69 72 75 73 }

    condition:
        $my_text_string or $my_hex_string
}
