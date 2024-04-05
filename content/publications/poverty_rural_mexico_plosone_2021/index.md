---
title: "Examining gender inequalities in factors associated with income poverty in Mexican rural households"
subtitle: "published in Plos ONE"
date: "2021-11-04"
date_end: "2021-11-04"
featured: true
show_post_time: false
author: "Juan TORRES MUNGUÍA & Inmaculada Martínez-Zarzoso"
location: ""
draft: false
# layout options: single, single-sidebar
layout: single
categories:
- journal-articles
- poverty
- 2021
links:
- icon: file-pdf
  icon_pack: fas
  name: PDF
  url: https://journals.plos.org/plosone/article/file?id=10.1371/journal.pone.0259187&type=printable
- icon: link
  icon_pack: fas
  name: DOI
  url: https://doi.org/10.1371/journal.pone.0259187
- icon: database
  icon_pack: fas
  name: Data
  url: https://figshare.com/articles/dataset/Essays_on_structured_additive_regression_models_applied_to_data_in_development_economics_Electronic_material_/21183271
- icon: code
  icon_pack: fas
  name: Code
  url: https://figshare.com/articles/dataset/Essays_on_structured_additive_regression_models_applied_to_data_in_development_economics_Electronic_material_/21183271
---

<h4> Abstract </h4>
According to 2016 official estimates, almost 60% of the rural population in Mexico (16.9 million people) had income levels below the poverty line, and approximately 29.2% (8.3 million) could not even afford the basic food basket. Whereas most poverty research disregards gender and exclusively analyzes average income or the expected probability of being poor, we depart from these approaches by examining the effect of potential risk factors on two of the lowest quantiles of income-to-poverty ratio distribution, namely the corresponding to poor and extremely poor families. Focusing on identifying heterogeneous effects according to the sex of the household head, we apply additive quantile models to a cross-sectional dataset containing information on 4,434 women-headed and 14,877 men-headed households. For each model, we introduce 45 variables at the individual/household, community, and regional levels. Two major contributions emerge from this paper. First, the identification of a subset of significant factors whose effect is independent of the head’s sex and is relevant for poor and extremely poor families. This is found for the variables credit card ownership, access to basic housing services, education level, and satisfaction with public services. Second, results also identify a subset of significant factors with an uneven effect on income according to the sex of the head that is observed both in the poor and extremely poor households. Variables having this gendered effect are the community’s income inequality, municipal human development, social networks, access to social security, and gender-based violence against women in the public sphere. Out of these, particularly relevant is the effect of the last three factors, whose association with income has not been explored before for rural Mexico and for which the bias among sexes increases as family income grows from extreme poverty to poverty level.

<h4 id="citation">Citation</h4>
<div id="citation-content"></div>

<script>
function generateCitationHTML(entry) {
  const authors = `<strong>${entry.author.replace(/[{}]/g, '').replace(/,(\s*)$/, '')}</strong>`;
  const year = entry.year.replace(/[{}]/g, '').replace(/,(\s*)$/, '');
  const title = entry.title.replace(/[{}]/g, '').replace(/,(\s*)$/, '');
  const volume = entry.volume.replace(/[{}]/g, '').replace(/,(\s*)$/, '');
  const number = entry.number.replace(/[{}]/g, '').replace(/,(\s*)$/, '');
  const journal = entry.journal.replace(/[{}]/g, '').replace(/,(\s*)$/, '');
  const url = entry.url.replace(/[{}]/g, '').replace(/,(\s*)$/, '');
  const doi = entry.doi.replace(/[{}]/g, '').replace(/,(\s*)$/, '');

  const citationHTML = `
    <p>${authors} (${year}) <em>${title}</em>. ${journal}, ${volume}(${number}). <a href="${url}" target="_blank">${doi}</a>.</p>
    <p>Download the article citation in BibTex format (compatible with BibDesk, LaTeX) <a href="cite.bib"><i class="fas fa-file-download"></i></a>.</p>
  `;
  
  return citationHTML;

}

  // Main function to fetch .bib file and generate HTML
  function main() {
    // AJAX request to fetch .bib file
    var xhr = new XMLHttpRequest();
    xhr.open("GET", "cite.bib", true);
    xhr.onreadystatechange = function() {
      if (xhr.readyState == 4 && xhr.status == 200) {
        // Parse BibTeX into JSON
        var bibData = parseBibtex(xhr.responseText);

        // Generate HTML for each entry
        var citationDiv = document.getElementById('citation-content');
        bibData.entries.forEach(entry => {
          const citationHTML = generateCitationHTML(entry);
          citationDiv.innerHTML += citationHTML;
        });
      }
    };
    xhr.send();
  }

  // Parse BibTeX into JSON
  function parseBibtex(bibtex) {
    // Split BibTeX into individual entries
    var entries = bibtex.split('\n\n');

    // Initialize an array to store parsed entries
    var parsedEntries = [];

    // Parse each entry
    entries.forEach(entry => {
      // Split entry into lines
      var lines = entry.split('\n');

      // Initialize an object to store parsed entry fields
      var parsedEntry = {};

      // Parse each field
      lines.forEach(line => {
        // Ignore empty lines and comments
        if (line.trim() !== '' && !line.startsWith('%')) {
          // Split line into key and value
          var parts = line.split('=');
          var key = parts[0].trim();
          var value = parts.slice(1).join('=').trim();

          // Store key-value pair in parsed entry
          parsedEntry[key] = value;
        }
      });

      // Add parsed entry to array
      parsedEntries.push(parsedEntry);
    });

    // Return parsed entries
    return { entries: parsedEntries };
  }

  // Run main function
  main();
</script>