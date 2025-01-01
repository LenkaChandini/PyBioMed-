# PyBioMed-  
## PyBioMed Code Enhancements
# Overview
This fork of the PyBioMed library includes updates to improve compatibility with modern Python versions, enhance functionality, and address deprecated methods in NumPy, SciPy, and other dependencies. The modifications ensure smoother integration with current environments and add error handling for better user experience.
________________________________________
# Key Changes
1. Compatibility Updates
•	Replaced deprecated numpy.float with float in multiple files to align with recent NumPy versions.
•	Updated deprecated scipy methods (triu, dot) to their NumPy equivalents (np.triu, np.dot).
2. Improved File Handling
•	Implemented context managers (with open()) for secure and efficient file reading and writing.
•	Enhanced PDB file download functionality to use HTTPS with the requests library, replacing FTP for better reliability and security.
3. Error Handling and Unicode Compatibility
•	Added proper exception handling for network-related operations (e.g., downloading PDB or UniProt files).
•	Ensured Unicode compatibility by decoding file content where required (e.g., GetProteinSequence function).
4. Dependency Management
•	Added missing imports for essential modules like numpy and requests in specific files.
________________________________________
# Modified Files
Below is a list of the modified files and key updates made in each:
1. connectivity.py
•	Line 365: Replaced numpy.float with float for NumPy array creation in CalculateChi3c.
•	Enhancement: Added import numpy as np for consistent NumPy usage.
2. cats2d.py
•	Line 40: Added import numpy as np.
•	Line 260: Replaced scipy.triu with np.triu.
•	Line 266: Replaced scipy.argwhere with np.argwhere.
3. estate.py
•	Line 51: Updated numpy.zeros(..., numpy.float) to numpy.zeros(..., float).
•	Added import warnings and import numpy as np.
4. GetProtein.py
•	Line 29: Added import requests.
•	Updated pdbDownload function to use HTTPS and requests.get.
•	Enhanced file extraction logic using context managers.
5. GetMol.py
•	Replaced FTP-based molecule downloads with HTTPS using requests.get.
•	Improved error handling for downloading and parsing SDF files.
6. constitution.py
•	Enhanced handling of RDKit vector outputs in the GetConstitutional function.
7. topology.py
•	Line 525: Replaced scipy.dot with np.dot.
8. GetProteinFromUniprot.py
•	Improved Unicode handling in the GetProteinSequence function.
________________________________________
# Benefits of These Changes
•	Modern Python Compatibility: Resolves issues with deprecated methods, ensuring the library works seamlessly with Python 3.9+.
•	Improved Reliability: Secure HTTPS downloads replace outdated FTP protocols.
•	Enhanced Readability: Cleaner and more maintainable code through consistent practices (e.g., context managers).
•	Error Resilience: Additional error handling ensures smoother execution in edge cases.
________________________________________
# Testing
The updates have been tested with:
•	Sample molecules for connectivity and estate descriptor calculations.
•	Protein sequence retrieval using PDB and UniProt IDs.
•	Molecule downloads from DrugBank using valid IDs.
________________________________________
# Contributing
Contributions are welcome to further enhance this library. Please:
1.	Fork the repository.
2.	Submit a pull request with detailed descriptions of changes.
