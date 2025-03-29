def transcription(dna_sequence):
    return dna_sequence.replace('T', 'U')
def reverse_transcription(rna_sequence):
    return rna_sequence.replace('U', 'T')
def translation(rna_sequence):
    codon_table = {
    'AUG': 'Methionine', 'UUU': 'Phenylalanine', 'UUC': 'Phenylalanine',
    'UUA': 'Leucine', 'UUG': 'Leucine', 'CUU': 'Leucine', 'CUC': 'Leucine',
    'CUA': 'Leucine', 'CUG': 'Leucine', 'AUU': 'Isoleucine', 'AUC': 'Isoleucine',
    'AUA': 'Isoleucine', 'GUU': 'Valine', 'GUC': 'Valine', 'GUA': 'Valine',
    'GUG': 'Valine', 'UCU': 'Serine', 'UCC': 'Serine', 'UCA': 'Serine',
    'UCG': 'Serine', 'AGU': 'Serine', 'AGC': 'Serine', 'CCU': 'Proline',
    'CCC': 'Proline', 'CCA': 'Proline', 'CCG': 'Proline', 'ACU': 'Threonine',
    'ACC': 'Threonine', 'ACA': 'Threonine', 'ACG': 'Threonine', 'GCU': 'Alanine',
    'GCC': 'Alanine', 'GCA': 'Alanine', 'GCG': 'Alanine', 'UAU': 'Tyrosine',
    'UAC': 'Tyrosine', 'UAA': 'Stop', 'UAG': 'Stop', 'UGA': 'Stop',
    'CAU': 'Histidine', 'CAC': 'Histidine', 'CAA': 'Glutamine', 'CAG': 'Glutamine',
    'AAU': 'Asparagine', 'AAC': 'Asparagine', 'AAA': 'Lysine', 'AAG': 'Lysine',
    'GAU': 'Aspartic acid', 'GAC': 'Aspartic acid', 'GAA': 'Glutamic acid',
    'GAG': 'Glutamic acid', 'UGU': 'Cysteine', 'UGC': 'Cysteine', 'UGG': 'Tryptophan',
    'CGU': 'Arginine', 'CGC': 'Arginine', 'CGA': 'Arginine', 'CGG': 'Arginine',
    'AGA': 'Arginine', 'AGG': 'Arginine', 'GGU': 'Glycine', 'GGC': 'Glycine',
    'GGA': 'Glycine', 'GGG': 'Glycine'
    }
    protein_sequence = []
    for i in range(0, len(rna_sequence), 3):
        codon = rna_sequence[i:i+3]
        protein_sequence.append(codon_table.get(codon, 'Unknown'))
    return ' \n'.join(protein_sequence)
print("Choose an operation: ")
print("1. Transcription (DNA to RNA)")
print("2. Translation (RNA to Protein)")
print("3. Reverse Transcription (RNA to DNA)")
choice = int(input("Enter the number corresponding to your choice: "))
if choice>4 :
  print("Invalid choice. Please try again.")
else:
  sequence = input("Enter the sequence: ").upper()
  if choice == 1:
      print("Transcribed RNA sequence:", transcription(sequence))
  elif choice == 2:
      print("Translated protein sequence:", translation(sequence))
  elif choice == 3:
      print("Reverse transcribed DNA sequence:", reverse_transcription(sequence))
  else:
      print("Invalid choice. Please try again.")
