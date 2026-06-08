{
  name: "NameOfWebsite",
  buildUrl: (sub, yr, seas, pap) => {
    // 1. SUBJECT DICTIONARY (Optional)
    // Use this if the website puts files into folders by name (like /physics/) instead of numbers (like /9702/)
    const subjectNames = {
      "9709": "mathematics",
      "9702": "physics",
      "9701": "chemistry",
      "9700": "biology",
      "9618": "computer-science"
    };
    
    // 2. SEASON DICTIONARY (Optional)
    // Use this if the website writes out full season names (like /march/) instead of letters (like /m/)
    const seasonNames = {
      "m": "march",
      "s": "may-june", // or "june", "summer", etc.
      "w": "october-november" // or "november", "winter", etc.
    };
    
    // 3. VARIABLE PREPARATION
    // Fetch translated values, or fallback to the original code if not found in the dictionary
    const folderName = subjectNames[sub] || "subject";
    const seasonWord = seasonNames[seas] || seas;
    const fullYear = `20${yr}`; // Turns "25" into "2025"
    
    // 4. THE URL CONSTRUCTOR
    // Assemble the parts to match the exact URL structure of the website.
    // Remember to use backticks ( ` ) and ${variableName} to drop the values in.
    return `https://example.com/path/to/files/${folderName}/${fullYear}/${sub}_${seas}${yr}_ms_${pap}.pdf`;
  }
}
