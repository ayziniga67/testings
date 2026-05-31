# testing

//for adding new sources
// Drop this right under the PapersDaddy block:
{
  name: "ExampleDB",
  buildUrl: (sub, yr, seas, pap) => {
    const seasonCodes = { "m": "01", "s": "02", "w": "03" };
    const fullYear = `20${yr}`;
    const code = seasonCodes[seas] || "01";
    
    return `https://example-papers.com/files/${sub}/${fullYear}/term-${code}/paper_${pap}.pdf`;
  }
}

//sAME EXAMPLE
{
  name: "NumericDatabase",
  buildUrl: (sub, yr, seas, pap) => {
    // The right side is changed to numbers because the target website uses numbers in its URLs
    const seasonCodes = { 
      "m": "1",  // March becomes session 1
      "s": "2",  // June becomes session 2
      "w": "3"   // November becomes session 3
    };
    
    const fullYear = `20${yr}`;
    const sessionNum = seasonCodes[seas] || "1";
    
    // Example output URL: https://numeric-site.com/9702/2026/session-2/paper-21.pdf
    return `https://numeric-site.com/${sub}/${fullYear}/session-${sessionNum}/paper-${pap}.pdf`;
  }
}
