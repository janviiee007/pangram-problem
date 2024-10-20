# pangram-problem
A pangram is a sentence that contains every letter of the English alphabet at least once.
#include <iostream>
#include <string>
using namespace std;

class Solution {
public:
    bool checkIfPangram(string sentence) {
        // Create a boolean array of size 26 to track the presence of each letter
        bool seen[26] = {false};
        
        // Iterate through the sentence and mark the letters as seen
        for (char c : sentence) {
            seen[c - 'a'] = true;
        }
        
        // Check if all letters are present
        for (bool exists : seen) {
            if (!exists) {
                return false; // If any letter is missing, return false
            }
        }
        
        return true; // All letters are present, return true
    }
};

int main() {
    Solution solution;
    string s1 = "thequickbrownfoxjumpsoverthelazydog";
    string s2 = "leetcode";
    
    cout << "Output for s1: " << solution.checkIfPangram(s1) << endl;  // Output: true
    cout << "Output for s2: " << solution.checkIfPangram(s2) << endl;  // Output: false
    
    return 0;
}

