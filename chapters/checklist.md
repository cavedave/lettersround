# Chapter Preparation Checklist

## Chapter 1 - Out Words

### Steps
- [x] Create word list
- [ ] Create initial MD file
  ```bash
  # Create the file with basic structure
  cat > chapters/ch1.md << 'EOF'
  # Chapter 1 - Out Words

  ## Word List and Meanings

  ## Games

  ### 1.1 Word Search Grid

  ### 1.2 Cloze Recognition

  ### 1.3 Letters Round Recognition

  ## Review
  EOF
  ```
- [ ] Generate word search puzzle
  ```bash
  # Generate word search with PDF and PNG output
  python utils/wordsearch.py OUTAGE OUTENED OUTLIER OUTSEEN OUTWEAR RAINOUT READOUT RIDEOUT SOUTANE --chapter 1
  ```
- [ ] Generate cloze recognition puzzle
  ```bash
  # TODO: Create cloze puzzle generator utility
  ```
- [ ] Generate letters round puzzle
  ```bash
  # TODO: Create letters round generator utility
  ```
- [ ] Add review section
  ```bash
  # TODO: Create review section generator utility
  ```
- [ ] Add word meanings and explanations
- [ ] Final proofreading and formatting

**Words:**
```
OUTAGE, OUTENED, OUTLIER, OUTSEEN, OUTWEAR, RAINOUT, READOUT, RIDEOUT, SOUTANE
```

## Chapter 2 - Animals in Disguise

### Steps
- [x] Create word list
- [ ] Create initial MD file
  ```bash
  # Create the file with basic structure
  cat > chapters/ch2.md << 'EOF'
  # Chapter 2 - Animals in Disguise

  ## Word List and Meanings

  ## Games

  ### 2.1 Word Search Grid

  ### 2.2 Cloze Recognition

  ### 2.3 Letters Round Recognition

  ## Review
  EOF
  ```
- [ ] Generate word search puzzle
  ```bash
  # Generate word search with PDF and PNG output
  python utils/wordsearch.py AGOUTI GOATEE GOATIER ODONATE RADIOLE RODENTIA ROTALINE --chapter 2
  ```
- [ ] Generate cloze recognition puzzle
  ```bash
  # TODO: Create cloze puzzle generator utility
  ```
- [ ] Generate letters round puzzle
  ```bash
  # TODO: Create letters round generator utility
  ```
- [ ] Add review section
  ```bash
  # TODO: Create review section generator utility
  ```
- [ ] Add word meanings and explanations
- [ ] Final proofreading and formatting

**Words:**
```
AGOUTI, GOATEE, GOATIER, ODONATE, RADIOLE, RODENTIA, ROTALINE
```

## Notes
- Word search puzzles should be 15x15 grid
- Use level 3 difficulty for consistent challenge
- Save images in `images/chXX/` directory
- Use consistent naming: `chXX_wordsearch.png`, `chXX_cloze.png`, etc.
- Include width=100% for word search images, width=90% for others
- Each chapter MD file should follow the standard structure:
  - Title (# Chapter X — Theme)
  - Introduction paragraph
  - Word List and Meanings section
  - Games section (Word Search, Cloze, Letters Round)
  - Review section
  - Next chapter preview 