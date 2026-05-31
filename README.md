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
