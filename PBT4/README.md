THE VOSS EXPERIMENT
README – Kodi i projektit
1. Teknologjitë
•	Unity 3D – krijimi i ambientit dhe zhvillimi i lojës.
•	C# – programimi i logjikës dhe mekanikave të lojës.
•	URP – renderimi dhe ndriçimi.
•	Unity UI – menytë, terminalet dhe mesazhet.
2. Menaxhimi i lojës
•	GameManager.cs – menaxhon gjendjen e përgjithshme të lojës.
•	GameState.cs – ruan progresin dhe gjendjen e lojës.
•	GameFlags.cs – ruan shenjat e progresit.
•	AttemptManager.cs – menaxhon pesë tentativat.
•	SceneTransitionManager.cs – menaxhon kalimin ndërmjet skenave.
3. Lëvizja dhe ndërveprimi
•	FirstPersonController.cs – kontrollon lëvizjen e lojtarit.
•	PlayerInteractor.cs – mundëson ndërveprimin me objektet.
•	InspectionController.cs – mundëson inspektimin e objekteve.
•	DoorController.cs – menaxhon hapjen dhe mbylljen e dyerve.
•	EvidencePickup.cs – menaxhon marrjen e provave.
4. Enigmat
•	PerceptionPuzzle.cs – logjika e enigmës PERCEPTION.
•	ReasonPuzzle.cs – logjika e enigmës REASON.
•	MemoryPuzzle.cs – logjika e enigmës MEMORY.
•	PuzzleManager.cs – menaxhon enigmat.
•	KeypadController.cs – kontrollon futjen e kodeve.
•	MemoryDoorController.cs – menaxhon portën MEMORY.
•	BalanceScaleController.cs – menaxhon mekanikën e peshores.
•	BlackBoxController.cs – menaxhon kutinë e zezë.
•	MirrorDisplay.cs – menaxhon paraqitjen e reflektimeve.
•	TerminalController.cs – menaxhon terminalet e enigmave.
5. Historia dhe përfundimi
•	MainMenuController.cs – menaxhon menynë kryesore.
•	InvitationSequence.cs – menaxhon sekuencën e ftesës.
•	LabEntranceSequence.cs – menaxhon hyrjen në laborator.
•	EvidenceManager.cs – ruan dhe menaxhon provat.
•	FinalInvestigationController.cs – menaxhon hetimin përfundimtar.
•	VideoInvestigationController.cs – menaxhon hetimin përmes këndeve të kamerës.
•	FinalQuestionTerminal.cs – menaxhon pyetjen përfundimtare.
•	FinalRevealController.cs – menaxhon zbulimin e së vërtetës.
•	TheatreEndingController.cs – menaxhon përfundimin në teatër.
•	GameRestartController.cs – menaxhon rifillimin e lojës.
6. Ndërfaqja dhe audio
•	UIManager.cs – menaxhon ndërfaqen e lojës.
•	UIFactory.cs – krijon elementet e ndërfaqes.
•	KeypadPanel.cs – menaxhon panelin e kodeve.
•	EvidencePanel.cs – paraqet provat.
•	ChoicePanel.cs – paraqet alternativat.
•	VideoControlsPanel.cs – menaxhon kontrollet e videos.
•	AudioManager.cs – menaxhon audion.
•	AudioLibrary.cs – organizon burimet audio.
•	ProceduralAudio.cs – krijon efekte audio përmes kodit.
7. Ndërtimi i skenave
•	VossSceneBuilder.cs – përgatit strukturën e skenave.
•	MainMenuBuilder.cs – ndërton menynë kryesore.
•	InvitationBuilder.cs – ndërton skenën e ftesës.
•	LaboratoryBuilder.cs – ndërton ambientin e laboratorit.
•	TheatreBuilder.cs – ndërton ambientin e teatrit.
•	VossBuildKit.cs – përmban funksione ndihmëse për ndërtimin e skenave.
8. Logjika kryesore e lojës
1.	Lojtari merr ftesën dhe biletën me numrin 7314.
2.	Në PERCEPTION, zgjidh enigmën e reflektimit dhe zbulon READ.
3.	Në REASON, zgjidh enigmën logjike dhe zbulon BACKWARDS.
4.	Në MEMORY, përdor provat për të gjetur kodin 4137.
5.	Në Final Investigation, analizon ngjarjen nga kënde të ndryshme.
6.	Lojtari zbulon se Elias Voss nuk hyri kurrë në dhomën transparente.
7.	Loja përfundon me mesazhin EXPERIMENT 001 — COMPLETE.

