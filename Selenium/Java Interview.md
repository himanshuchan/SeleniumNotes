1. Find the duplicate and distinct values in arrays or strings
2. Find the max and min values
3. Find the 2nd largest or 2nd smallest values
4. Removal of duplicate values
5. Occurrence of each characters in a string
6. Palindrome in string or number
7. Prime number
8. Fibonacci series
9. Sum of digits
10. Longest substring
11. Longest palindrome substring
12. Reverse of string
13. Reverse of each character of a string on its own place
14. Reverse half character of a string
15. Longest Palindrome substring
16. All permutations and combinations of a number
17. Removal of special characters from a string
18. Arrange words and int side by side in a string
19. OOPS concept definitions
20. This, Super and final words

**100 Java String Questions with Answers for Selenium Java Interviews**
 
**📘** **Category 1: String Basics (1–20)**

1. **Reverse a string****￼**return new StringBuilder(str).reverse().toString();
2. **Check if a string is palindrome****￼**return str.equals(new StringBuilder(str).reverse().toString());
3. **Convert string to char array****￼**char[] chars = str.toCharArray();
4. **Compare two strings (== vs equals)****￼**'==' checks reference, 'equals()' checks content.
5. **Check if string contains a substring****￼**str.contains("sub");
6. **Find length of a string****￼**int len = str.length();
7. **Convert string to uppercase/lowercase****￼**str.toUpperCase(); str.toLowerCase();
8. **Replace all occurrences of a character****￼**str.replace('a', 'b');
9. **Count vowels and consonants****￼**Use loop & check char in 'aeiouAEIOU'
10. **Count spaces in a string****￼**int count = 0; for (char c : str.toCharArray()) if (c == ' ') count++;
11. **Count digits and letters****￼**Use Character.isDigit() & isLetter()
12. **Check if two strings are anagrams****￼**Sort and compare both strings.
13. **Count number of words****￼**str.trim().split("\\s+").length;
14. **Capitalize first letter of each word****￼**Split → capitalize → join
15. **Remove all spaces from string****￼**str.replace(" ", "");
16. **Find first non-repeating character****￼**Use LinkedHashMap with frequency count
17. **Find first repeating character****￼**Use Set to track seen characters
18. **Remove duplicate characters****￼**Use Set + StringBuilder
19. **Swap two strings without third variable****￼**Use concatenation + substring
20. **Reverse each word in a string****￼**Split → reverse → join
 
**📗** **Category 2: String Operations & Patterns (21–40)**

1. **Sort characters alphabetically****￼**char[] arr = str.toCharArray(); Arrays.sort(arr);
2. **Replace vowels with ***￼str.replaceAll("[aeiouAEIOU]", "*");
3. **Toggle case of each character****￼**Use Character.isUpperCase() etc.
4. **Remove punctuation from string****￼**str.replaceAll("[^a-zA-Z0-9 ]", "");
5. **Find duplicate words****￼**Use HashMap\<String, Integer\>
6. **Remove duplicate words****￼**Use LinkedHashSet
7. **Find frequency of each character****￼**Use HashMap\<Character, Integer\>
8. **Check if string starts/ends with substring****￼**str.startsWith("sub"), str.endsWith("xyz")
9. **Find longest word in sentence****￼**Split → compare lengths
10. **Replace each word with its length****￼**Map each word to its length
11. **String compression** (e.g., aabcc → a2b1c2)￼Use loop + StringBuilder
12. **Print all substrings****￼**Use nested loop and substring(i, j)
13. **Generate all permutations****￼**Recursion + backtracking
14. **Find common characters between two strings****￼**Use Set intersection
15. **Count occurrence of each word****￼**HashMap\<String, Integer\>
16. **Convert to title case****￼**Capitalize first character of each word
17. **Format string using String.format()****￼**String.format("%s - %d", str, num);
18. **Check if string is numeric****￼**str.matches("\\d+");
19. **Reverse using recursion****￼**reverse(str.substring(1)) + str.charAt(0);
20. **Check if only digits exist****￼**str.matches("\\d+");
 
**📙** **Category 3: Regex (41–60)**

1. **Validate email****￼**str.matches("^[A-Za-z0-9+_.-]+@(.+)$");
2. **Validate phone number****￼**str.matches("\\d{10}");
3. **Extract digits****￼**str.replaceAll("\\D", "");
4. **Words starting with capital letter****￼**Regex: [\\b[A-Z][a-zA-Z]*\\b](file:///\\b[A-Z][a-zA-Z]*\\b)
5. **Validate password strength****￼**Regex with conditions (e.g., digits, length)
6. **Remove special characters****￼**str.replaceAll("[^a-zA-Z0-9]", "");
7. **Match date pattern****￼**Regex: [\\d{2}-\\d{2}-\\d{4}](file:///\\d{2}-\\d{2}-\\d{4})
8. **Replace multiple spaces with one****￼**str.replaceAll("\\s+", " ");
9. **Extract hashtags****￼**Regex: #\\w+
10. **Extract domain from email****￼**str.split("@")[1];
11. **Validate IP address****￼**Regex: [\\b(?:\\d{1,3}\\.){3}\\d{1,3}\\b](file:///\\b\(?:\\d{1,3}\\.\){3}\\d{1,3}\\b)
12. **Split camelCase****￼**str.replaceAll("([a-z])([A-Z])", "$1 $2");
13. **Check only alphabets****￼**str.matches("[a-zA-Z]+")
14. **Validate PAN format****￼**str.matches("[A-Z]{5}[0-9]{4}[A-Z]{1}");
15. **Validate URL****￼**str.matches("https?://.*")
16. **Extract all numbers****￼**Use Matcher with pattern [\\d+](file:///\\d+)
17. **Quoted strings****￼**Regex: '([^']*)'
18. **Text between brackets****￼**Regex: \\[(.*?)\\]
19. **Count pattern occurrences****￼**Use Matcher.find() with counter
20. **Remove HTML tags****￼**str.replaceAll("\<[^\>]*\>", "");
 
**📒** **Category 4: StringBuilder/StringBuffer (61–75)**

1. **Reverse using StringBuilder****￼**new StringBuilder(str).reverse();
2. **Append multiple strings****￼**sb.append(a).append(b);
3. **Compare String vs StringBuilder****￼**String = immutable; SB = mutable
4. **Thread safety of StringBuffer****￼**Yes (synchronized methods)
5. **Remove characters****￼**sb.delete(start, end);
6. **Replace characters****￼**sb.replace(start, end, "new");
7. **Insert in middle****￼**sb.insert(pos, "insert");
8. **Reverse words****￼**Reverse each word using SB
9. **Create palindrome from half****￼**Append reverse of substring
10. **Compare StringBuilder objects****￼**Use sb1.toString().equals(sb2.toString())
 
**📕** **Category 5: Automation-Relevant Strings (76–90)**

1. **Extract OTP****￼**Use regex or substring logic
2. **Extract password from text****￼**str.substring(indexOf("'")+1, lastIndexOf("'"));
3. **Parse CSV-style string****￼**str.split(",");
4. **Extract token from response****￼**Substring between known keys
5. **Create dynamic XPath****￼**"//input[@name='" + value + "']"
6. **Validate UI text****￼**driver.findElement(...).getText().equals(expected);
7. **Compare element text****￼**Assert.assertEquals(actual, expected);
8. **Build test name from values****￼**"TC_" + scenario + "_" + status
9. **Remove dynamic logs****￼**Regex + static parts
10. **Normalize error messages****￼**Use regex replaceAll("\\d+", "")
11. **Generate random string****￼**UUID.randomUUID().toString();
12. **Mask password****￼**str.replaceAll(".", "*");
13. **Extract status from log****￼**log.split(" ")[statusIndex];
14. **Format timestamp****￼**new SimpleDateFormat("yyyy-MM-dd").format(new Date());
15. **Unique test data string****￼**"Test_" + System.currentTimeMillis();
16. **List to CSV string****￼**String.join(",", list);
17. **Replace template values****￼**template.replace("{user}", username);
18. **String from char array****￼**new String(charArray);
19. **URL-safe string****￼**URLEncoder.encode(str, "UTF-8");
20. **Check file extension****￼**file.endsWith(".pdf")
 
**📓** **Category 6: Edge & Advanced (91–100)**

1. **Handle null/empty****￼**str != null && !str.isEmpty()
2. **Split manually****￼**Use indexOf() and loop
3. **Replace nth occurrence****￼**Use regex and Matcher
4. **Count palindromic substrings****￼**Nested loop checking isPalindrome()
5. **Check if one string is rotation of another****￼**(s1 + s1).contains(s2)
6. **Convert int to string****￼**String.valueOf(num);
7. **Convert string to ASCII****￼**Loop with (int) c
8. **Remove nth character****￼**str.substring(0, n) + str.substring(n+1);
9. **Encrypt (Caesar cipher)****￼**Shift each char by n using (char)(c + n)
10. **Decode Base64****￼**new String(Base64.getDecoder().decode(str));