## XML_RPC2


## Usage
Clone to PEAR_path/XML, for example /usr/share/php/XML

## Correction
Just this:
```bash
alex@vostok:/Volumes/HD/dev/XML_RCP2$ sed -n -e '75,80p' RPC2/Server/Input/RawPostData.php
    public function readRequest()
    {
        // Alexandre Espinosa Menor (2012-07-06): force this global
        $GLOBALS['HTTP_RAW_POST_DATA'] = file_get_contents('php://input');

        if (!isset($this->input) && !isset($GLOBALS['HTTP_RAW_POST_DATA'])) throw new XML_RPC2_ConfigException('XML_RPC2_Server_Input_RawPostData requested but PHP config does not show GLOBALS[\'HTTP_RAW_POST_DATA\'] as available');
```
