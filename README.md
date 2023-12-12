# chatgpt-json-to-html-convert-code
This is chatgpt-json-to-html-convert-code

-PHP/Laravel

------ json structure to html code type in controller (api post)--------
$result = json_decode($response)->choices[0]->message->content;
        $paragraphs = explode("\n", $result); // Split the text into paragraphs
        $formattedText = '';
        foreach ($paragraphs as $p) {
        $includesA = strpos($p, '<br>') !== false;
        if ($includesA) {
            $formattedText .= $p; // Add paragraph tags to each paragraph
        } else {
            $formattedText .= "<p>$p</p>"; // Add paragraph tags to each paragraph
        }
}

  return response()->json([
      'message' => $formattedText

  ]);

-------- html code convert to html dom in view (Vue) -----------------

  const formatcontent = props.message.content;
  <p class="block text-sm fomart-content" >
     <div v-html= "formatcontent" ></div>
  </p>

.fomart-content > div > p {
  margin-bottom: 20px;
}   

============================================================
- React/Next.JS
  
const paragraphs = result.split('\n'); // Split the text into paragraphs

  let formattedText = '';
  for (const p of paragraphs) {
    let includesA = p.includes('<br>');
    if (includesA)
      formattedText += `${p}`; // Add paragraph tags to each paragraph
    else formattedText += `<p>${p}</p>`; // Add paragraph tags to each paragraph
  }

  
        
