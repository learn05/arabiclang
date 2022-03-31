# arabiclang for domPDF

this is solution for the dompdf Laravel Plugin

I found a solution for the dompdf to solve the Arabic text in PDF Generator, this is for Laravel.
also every PHP developer can get an adantage and easy to use to this library to add arabic text to different kind of PHP PDF genrators.

هذه المكتبة والطريقة التالية تقدم حل لاظهار اللغة العربية لأضافة domPDF لارافيل, والطريقة كالتالي:
<ol>
  <li>Create a Folder inside App Called Library.</li>
  
  <li>Upload the Repo to the Library Folder.</li>
  
  <li>Open the text.php file, that is located in:<br>
    <code>\vendor\dompdf\dompdf\src\Renderer</code>
  </li>
    
  <li>find the below almost in #90 line.<br>
    <code>$this->_canvas->text($x, $y, $text,
            $font, $size,
            $style->color, $word_spacing, $char_spacing);
    </code>
  </li>
  
  <li>Add the Below Code Above it:<br>
    <code>
    if (strtolower($style->direction) == 'rtl') {
        $Arabic = new \App\Libraries\I18N\I18N_Arabic('Glyphs');
        $text = $Arabic->utf8Glyphs($text);
        }
    </code>
  </li>
  
</ol>
<h4>Original Code at this link <a href="https://sourceforge.net/projects/ar-php/">Click Me</a></h4>
<h4>this Code is Credited to <b>"Dominique Abou Samah"</b>, Thanks to him</h4>
<p>URL of the Original Answer is <a href="https://stackoverflow.com/questions/67462233/laravel-dompdf-arabic-characters-generate-pdf-error">Click Here</><p>


