# PHP function

#### How to use the image-resize plugin for input files?

```
function uploadImage($fileImage, $filekey, $filevalue, $firstnameImage ) {
    $filename = $firstnameImage.uniqid(). ".jpeg";
    $tmp = $fileImage['tmp_name'][$filekey];

    $image = new ImageResize($tmp);
    $image->resize(500, 400);
    if ($image->save(ROOT_DIR . '/stocks/' . $filename)){
        return $filename;
    } else {
        $res = array();
        $res["status"] = "error";
        $res["err_code"] = "file image upload";

        echo json_encode($res);
        exit();
    }
}


``` 
#### Learn more at https://github.com/gumlet/php-image-resize

#### how to get file to work with https?

``` 
function getSslPage($url) {
    $ch = curl_init();
    curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, FALSE);
    curl_setopt($ch, CURLOPT_HEADER, false);
    curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
    curl_setopt($ch, CURLOPT_URL, $url);
    curl_setopt($ch, CURLOPT_REFERER, $url);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, TRUE);
    $result = curl_exec($ch);
    curl_close($ch);
    return $result;
}
``` 
#### Note: This disables SSL verification, meaning the security offered by HTTPS is lost. Only use this code for testing / local development

#### Thanks

Win'ny Freedom
