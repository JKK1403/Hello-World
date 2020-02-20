# Hello-World


$configuration = DocRaptor\Configuration::getDefaultConfiguration();
$configuration->setUsername("YOUR_API_KEY_HERE");
// $configuration->setDebug(true);
$docraptor = new DocRaptor\DocApi();

$doc = new DocRaptor\Doc();
$doc->setTest(true);                                                   // test documents are free but watermarked
$doc->setDocumentContent("<html><body>Hello World</body></html>");     // supply content directly
// $doc->setDocumentUrl("http://docraptor.com/examples/invoice.html"); // or use a url
$doc->setName("docraptor-php.pdf");                                    // help you find a document later
$doc->setDocumentType("pdf");                                          // pdf or xls or xlsx
// $doc->setJavascript(true);                                          // enable JavaScript processing
// $prince_options = new DocRaptor\PrinceOptions();                    // pdf-specific options
// $doc->setPrinceOptions($prince_options);
// $prince_options->setMedia("screen");                                // use screen styles instead of print styles
// $prince_options->setBaseurl("http://hello.com");                    // pretend URL when using document_content

$create_response = $docraptor->createDoc($doc);
