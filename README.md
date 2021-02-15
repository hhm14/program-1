# program-1
3320 program 1

Solution:

//copy and paste from here down 
//page 33 exercise 2.14
class Solution {
public:
    vector<vector<int>> ans; //return value
    vector<vector<int>> permute(vector<int>& nums) {
    int elements = nums.size(); // num elements given
    bookalgo(nums, elements, ans);
    return ans;
    }
    
    void bookalgo(vector<int>& nums, int elements, vector<vector<int>>& ans) 
    {
        if(elements == 1) { //base case, pushes singular elements into ans generating permutations with unlocked elements
            ans.push_back(nums);
        }
        else 
        {
            bookalgo(nums, elements-1, ans); //permutates while locking one element into the final index, decreases size
            for(int i = 0; i < elements-1; ++i) 
            {
                if (elements %2 == 1) // odd
                { 
                	swap(nums[0], nums[elements-1]);
                }
                else // even
                { 
                 	swap(nums[i], nums[elements-1]);
                }
                bookalgo(nums, elements-1, ans); // decreasing size again 
            }
        }
    }
};

