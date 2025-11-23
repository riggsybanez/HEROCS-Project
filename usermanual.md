HEROCS User Manual
HomeHazard Evaluation and Risk Object Classification System
 Version 2.0 | June 2025

Table of Contents
•         Introduction
•         Getting Started
•         Using HEROCS
•         Understanding Results
•         Safety Recommendations
•         Troubleshooting
•         Frequently Asked Questions

Introduction
What is HEROCS?
HEROCS (HomeHazard Evaluation and Risk Object Classification System) is a mobile application designed to help parents and caregivers identify household hazards that pose risks to young children, especially toddlers aged 0-3 years[1]. Using your smartphone camera, HEROCS scans your home environment and automatically detects dangerous objects in real-time.
Key Features
• Real-time Hazard Detection: Identifies 24 types of household hazards using AI-powered computer vision
• Augmented Reality (AR) Visualization: Overlays hazard warnings directly on your camera view
• Multi-label Classification: Recognizes multiple risk types for each object (e.g., sharp, within reach, near edge)
• Household Danger Index (HDI): Provides an overall safety score for your environment
• Safety Recommendations: Offers practical advice for each detected hazard
•  On-device Processing: Works without internet connection, protecting your privacy
Why Use HEROCS?
Children aged 0-3 years spend over 70% of their waking hours indoors, where household accidents are a leading cause of injury[2]. HEROCS helps you proactively identify dangers before accidents happen, giving you peace of mind and keeping your children safe.

Getting Started
System Requirements
•         Android smartphone with ARCore support
•         Camera: Minimum 12 MP
•         Operating System: Android 7.0 or higher
•         Storage: 150 MB free space
•         No internet connection required after installation
Installation
1.   	Download the HEROCS APK file from herocsv2-preview-app-release.apk
2.  	Open the downloaded file on your Android device
3.  	Tap "Install" when prompted
4.  	Grant camera and storage permissions when requested
5.   	Launch HEROCS from your app drawer
First-Time Setup
When you first open HEROCS:
1.   	Read the welcome screen explaining the app's purpose
2.  	Grant camera permissions (required for hazard detection)
3.  	Review the quick tutorial showing how to scan rooms
4.  	Start scanning your home

Using HEROCS
Main Screen
The HEROCS home screen provides three scanning options:
•         AR Camera Scan: Real-time scanning with augmented reality overlays
•         Image Detection: Analyze a single photo from your gallery
•         Camera Scan: Quick scan mode without AR features
AR Camera Scan (Recommended)
This is the primary scanning mode for comprehensive hazard detection.
How to Use:
1.   	Tap "AR Camera Scan" from the home screen
2.  	Hold your phone horizontally at chest level (approximately 150 cm high)
3.  	Slowly pan across the room you want to scan
4.  	HEROCS automatically detects hazards every 7 seconds
5.   	Detected hazards appear as colored bounding boxes on your screen
Understanding the Display:
•       Red boxes: Highly dangerous objects (e.g., knives, toxic chemicals)
•       Orange boxes: High-risk objects (e.g., choking hazards, electrical cords)
•       Yellow boxes: Moderate-risk objects (e.g., sharp furniture corners)
•       Green boxes: Low-risk objects (e.g., secured items)
Interactive Features:
•       Tap any bounding box to view detailed information about that hazard
•       Pause button: Freezes detection to review current hazards
•       Resume button: Continues scanning after pause
•       Safety Report button: View overall environment assessment
Image Detection
Upload and analyze photos of your home.
How to Use:
1.   	Tap "Image Detection" from the home screen
2.  	Select a photo from your gallery
3.  	Wait for HEROCS to analyze the image (3-5 seconds)
4.  	Review detected hazards with bounding boxes
5.   	Tap hazards for detailed information
Best Practices:
•         Take photos in good lighting
•         Capture clear, focused images
•         Include entire room or specific areas of concern
•         Avoid blurry or dark photos
Camera Scan
Quick scanning mode without AR features.
How to Use:
1.   	Tap "Camera Scan" from the home screen
2.  	Point camera at area to scan
3.  	Tap "Scan" button to capture and analyze
4.  	Review results with hazard list

Understanding Results
Hazard Details
When you tap on a detected hazard, you'll see:
•        Object Name: Type of hazard (e.g., "Sharp Object", "Toxic Chemical")
•        Detection Confidence: How certain HEROCS is about the identification (0-100%)
•         Risk Level: Highly Dangerous, High Risk, Moderate Risk, or Low Risk
•         Risk Score: Numerical score (0.1-0.5) indicating severity
•         Hazard Labels: Multiple risk types (e.g., "sharp", "within reach", "near edge")
•         Safety Recommendation: Specific advice for this hazard
Household Danger Index (HDI)
The HDI provides an overall safety assessment of your scanned environment[3].
HDI Score Ranges:
HDI Score
Safety Level
Interpretation
0.1 - 0.19
Safe
Environment is generally safe
0.2 - 0.29
Unsafe
Significant risks present
0.3 - 0.39
Very Unsafe
Multiple hazards need attention
0.4 - 0.49
Highly Unsafe
Urgent intervention required
0.5
Critically Unsafe
Emergency action needed

 
Table 1: HDI Safety Level Interpretation
How HDI is Calculated:
The HDI is the average risk score of all detected hazards in the scanned area. Each hazard receives a score based on:
•         Object type (e.g., knife = 0.4-0.5, plastic toy = 0.1-0.2)
•         Position (floor level, within reach, elevated)
•         Context (near edge, unsecured, exposed)
Example:
If HEROCS detects 5 hazards with scores of 0.5, 0.5, 0.4, 0.3, and 0.2, the HDI would be:
HDI = (0.5 + 0.5 + 0.4 + 0.3 + 0.2) ÷ 5 = 0.38 (Very Unsafe)
Multi-Label Classification
HEROCS assigns multiple labels to each hazard to provide complete risk information:
Categorical Labels (inherent properties):
•         sharp, hot, electrical, poisonous, choking, heavy, fragile, flammable, toxic
Positional Labels (accessibility):
•         floor-level (0-30 cm): On the floor
•         within-reach (30-96 cm): Accessible to toddlers
•         elevated (>96 cm): Out of reach, safe
Contextual Labels (spatial relationships):
•         near-edge, at-edge, fall-risk, unsecured, secured, stored-properly
Example: A knife on a table edge might be labeled: "sharp", "within-reach", "near-edge", "unsecured"
The 96cm Safety Threshold
HEROCS uses 96 cm (approximately 3 feet) as the critical height threshold based on WHO Child Growth Standards[4]. This represents the average height of a 3-year-old child.
•         Below 96 cm: Objects are accessible to children
•         Above 96 cm: Objects are generally out of reach and safer
When scanning, HEROCS estimates object heights based on their position in the camera frame, assuming you're holding the phone at chest level (150 cm).

Safety Recommendations
Priority-Based Actions
HEROCS provides safety recommendations ranked by urgency:
URGENT (Red Flag):
•         Structural hazards (stairs without railings, unprotected balconies)
•         Objects near edges (fragile, sharp, or hard items)
•         Unstable furniture that could tip over
•         Exposed electrical wiring
•         Explosive or flammable materials
•         Drowning hazards (water buckets)
IMPORTANT (Orange Flag):
•         Sharp objects within reach
•         Hot items accessible to children
•         Poisonous substances unsecured
•         Heavy objects not anchored
SUGGESTED (Yellow Flag):
•         Minor hazards or properly secured items
•         Preventive measures for low-risk objects
Common Recommendations
For Sharp Objects (knives, scissors):
•         Store in locked drawers or high shelves above 96 cm
•         Use safety locks on drawers containing sharp items
•         Never leave sharp objects on counters or tables
For Toxic Chemicals (cleaners, medicines):
•         Store in high, locked cabinets above 96 cm
•         Keep in original containers with warning labels
•         Use child-proof caps on medications
•         Consider safer, non-toxic alternatives
For Electrical Hazards (cords, outlets):
•         Install tamper-resistant outlet covers
•         Secure cords with cord covers or behind furniture
•         Repair exposed wiring immediately
For Unstable Furniture:
•         Anchor furniture to walls with brackets or straps
•         Remove items from tops that children might climb to reach
•         Store stools and step ladders when not in use
For Choking Hazards (small toys, coins):
•         Keep small objects in high, locked containers
•         Regularly check floors and low surfaces
•         Use toys appropriate for child's age
For Hot Items (stoves, hot containers):
•         Use stove guards and turn pot handles inward
•         Place hot items on back burners
•         Never leave cooking unattended with children present
Room-Specific Guidelines
Kitchen:
•         Install stove guards
•         Lock cabinets containing chemicals and sharp objects
•         Store appliances unplugged when not in use
•         Use back burners for cooking
Bathroom:
•         Empty water buckets immediately after use
•         Lock medicine cabinets
•         Install toilet locks
•         Use non-slip mats in bathtub
Living Room:
•         Anchor TV and heavy furniture to walls
•         Cover sharp furniture corners with guards
•         Secure electrical cords behind furniture
•         Install safety gates for stairs
Bedroom:
•         Remove small objects from floors
•         Secure dressers and wardrobes to walls
•         Use cordless window blinds
•         Keep beds away from windows

Troubleshooting
Camera Issues
Problem: Camera won't initialize or shows black screen
Solutions:
•         Check camera permissions in phone settings
•         Restart the HEROCS app
•         Restart your phone
•         Ensure no other apps are using the camera
•         Clear app cache in settings
Problem: Camera preview is laggy or frozen
Solutions:
•         Close other apps running in background
•         Ensure adequate phone storage space
•         Update to latest Android version
•         Reduce screen brightness to improve performance
Detection Issues
Problem: HEROCS isn't detecting hazards
Solutions:
•         Ensure good lighting in the room
•         Hold phone steady at chest level
•         Move closer to objects (1-2 meters distance)
•         Clean camera lens
•         Wait for automatic detection cycle (7 seconds)
Problem: Too many false detections
Solutions:
•         Improve room lighting
•         Avoid scanning cluttered areas all at once
•         Focus on specific zones one at a time
•         Check detection confidence scores (lower confidence may indicate false positives)
Problem: Known hazards not detected
Solutions:
•         Ensure object is clearly visible in frame
•         Move camera to different angle
•         Improve lighting conditions
•         Note: HEROCS may not detect all hazards; use it as a tool alongside your own judgment
AR Issues
Problem: AR overlays not appearing
Solutions:
•         Ensure device supports ARCore
•         Grant all required permissions
•         Check for ARCore updates in Google Play Store
•         Restart app
Problem: Bounding boxes misaligned with objects
Solutions:
•         Hold phone more steadily
•         Ensure good lighting for AR tracking
•         Avoid rapid camera movements
•         Restart AR scan
App Performance
Problem: App crashes or freezes
Solutions:
•         Clear app cache and data
•         Ensure adequate phone storage (at least 500 MB free)
•         Close background apps
•         Restart phone
•         Reinstall HEROCS if problem persists

Frequently Asked Questions
Q: Does HEROCS require internet connection?
A: No. HEROCS performs all detection on your device, so it works completely offline after installation. This also means your photos never leave your phone, protecting your privacy.
Q: How accurate is HEROCS?
A: HEROCS achieves approximately 41.5% mean average precision (mAP) for hazard detection, with higher accuracy (60-99%) for well-represented hazard types like toxic chemicals and flammable objects[5]. Always use HEROCS as a supplementary tool alongside your own judgment.
Q: What hazards can HEROCS detect?
A: HEROCS can identify 24 types of household hazards including: sharp objects, choking hazards, toxic chemicals, electrical hazards, hot items, flammable objects, fragile items, heavy/unstable furniture, drowning hazards, and structural risks like unprotected stairs and balconies.
Q: Why is the 96 cm threshold important?
A: 96 cm represents the average height of a 3-year-old child according to WHO standards. Objects below this height are within reach of toddlers and pose greater risks.
Q: Can HEROCS work in low light conditions?
A: HEROCS performs best in good lighting. Detection accuracy decreases in low light. Use room lights or natural daylight for best results.
Q: How often should I scan my home?
A: Scan your home:
•         After rearranging furniture or décor
•         When bringing new items into the house
•         Monthly as a routine safety check
•         Before events where children will be present
Q: What should I do if HEROCS detects a hazard?
A: Follow the safety recommendation provided for each hazard. Priority actions include:
1.   	Immediately remove or secure highly dangerous items
2.  	Address urgent hazards (structural issues, unstable furniture)
3.  	Plan improvements for moderate risks
4.  	Maintain awareness of low-risk items
Q: Is HEROCS suitable for older children?
A: HEROCS is specifically designed for homes with toddlers aged 0-3 years. Older children have different safety needs that HEROCS may not fully address.
Q: Can HEROCS replace professional safety inspections?
A: No. HEROCS is a helpful screening tool, but professional safety inspections provide comprehensive assessments and expert recommendations. Use HEROCS as a supplement to professional advice.
Q: What if HEROCS doesn't detect a hazard I know is dangerous?
A: HEROCS may not identify all hazards, especially unique or uncommon items. Always trust your own judgment and take action on hazards you recognize, even if HEROCS doesn't flag them.
Q: How do I interpret the Household Danger Index (HDI)?
A: The HDI is an average risk score for your environment:
•         0.1-0.19 = Safe (routine monitoring)
•         0.2-0.29 = Unsafe (improvements needed)
•         0.3-0.39 = Very Unsafe (comprehensive audit required)
•         0.4-0.49 = Highly Unsafe (urgent intervention)
•         0.5 = Critically Unsafe (emergency action)
Q: Why does HEROCS detect some objects multiple times?
A: This can occur when:
•         Scanning from different angles
•         Objects appear in overlapping frames
•         Similar objects are present in the same area
Use the temporal smoothing feature (automatic) to reduce duplicates.
Q: Can I customize detection sensitivity?
A: Currently, detection thresholds are preset based on validation testing. Future versions may include customizable sensitivity settings.
Q: What devices are compatible with HEROCS?
A: HEROCS requires Android devices with ARCore support, minimum 12 MP camera, and Android 7.0 or higher. Check Google's ARCore supported devices list for compatibility.

Support and Contact
For technical support, feedback, or questions:
Email: herocs.support@example.com
 Development Team: University of the Immaculate Conception - College of Computer Studies
Academic Researchers:
•         Jayci Gabriel Acua
•         Zyle Adam Doctolero
•         Riggs Harvey Ybaez

Important Safety Notice
HEROCS is a screening tool to assist caregivers in identifying household hazards. It does not replace:
•         Parental supervision and judgment
•         Professional safety inspections
•         Common sense safety practices
•         Emergency preparedness
Always:
•         Supervise children closely
•         Trust your instincts about safety
•         Consult professionals for serious hazards
•         Keep emergency numbers accessible
•         Maintain smoke detectors and fire extinguishers

References
[1] Bronfenbrenner, U. (1979). The Ecology of Human Development. Harvard University Press.
[2] World Health Organization. (2008). World report on child injury prevention. https://www.who.int/publications/i/item/world-report-on-child-injury-prevention
[3] Celik, Y., Kaya, M., Akinci, A., & Korkut, S. (2015). Home and Environment Risk Rating Scale (HERRS): Development and validation study. Turkish Journal of Medical Sciences, 45(3), 698-707.
[4] WHO Multicentre Growth Reference Study Group. (2006). WHO Child Growth Standards: Length/height-for-age, weight-for-age, weight-for-length, weight-for-height and body mass index-for-age. WHO Press.
[5] HEROCS Development Team. (2025). HEROCS: An on-device mobile computer vision assessment system for hazard detection in household environments. Undergraduate thesis, University of the Immaculate Conception.

Version: 1.0
 Last Updated: June 2025
 Document Type: User Manual

