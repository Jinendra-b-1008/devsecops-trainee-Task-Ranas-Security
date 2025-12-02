Security notes on Dokcer 
    
1. Random images may contain malware or spyware
   Risk -> Image may contain malware, spyware, crypto-miners, or backdoors
   Impact -> Host machine can be compromised
             Sensitive environment variables can be stolen
   Mitigation -> Pull images only from trusted registries (Docker Hub Officials, AWS ECR etc)
               run security scans like Trivy
2. Images Containing Vulnerabilities
   Risk -> Containers may include unnecessary packages increasing attack surface
   Impact -> System becomes vulnerable to remote exploits
   Mitigation -> Use minimal base images (alpine, python:slim, distroless)
3. Large Image Size
   Risk -> Unnecessarily large images contain more tools, libraries, and binaries
   Impact -> Increased attack surface, Higher storage
   Mitigation -> Multi-stage builds, Use lightweight base images
4. Data Exfiltration Risks
   Risk -> Malicious images can scan mounted directories, Scripts inside the image can silently upload data
   Impact -> Leak of secrets, API keys, tokens and Loss of confidential data
   Mitigation -> Never mount host paths directly unless needed
       
