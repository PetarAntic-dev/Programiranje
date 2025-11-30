#include <iostream>
#include <queue>
#include <stack>
using namespace std;

// ===================== BT NODE =====================
struct BTNode {
    int val;
    BTNode *left, *right;

    BTNode(int v=0) : val(v), left(nullptr), right(nullptr) {}

    void insert(int value) {
        queue<BTNode*> q;
        q.push(this);

        while (!q.empty()) {
            BTNode* cur = q.front();
            q.pop();

            if (!cur->left) {
                cur->left = new BTNode(value);
                return;
            }
            if (!cur->right) {
                cur->right = new BTNode(value);
                return;
            }

            q.push(cur->left);
            q.push(cur->right);
        }
    }

    BTNode* find(int value) {
        if (val == value) {
            return this;
        }

        BTNode* f = nullptr;

        if (left) {
            f = left->find(value);
        }
        if (f) {
            return f;
        }

        if (right) {
            f = right->find(value);
        }

        return f;
    }

    void preorder() {
        cout << val << " ";
        if (left) {
            left->preorder();
        }
        if (right) {
            right->preorder();
        }
    }

    void inorder() {
        if (left) {
            left->inorder();
        }
        cout << val << " ";
        if (right) {
            right->inorder();
        }
    }

    void postorder() {
        if (left) {
            left->postorder();
        }
        if (right) {
            right->postorder();
        }
        cout << val << " ";
    }

    void preorder_stack() {
        stack<BTNode*> st;
        st.push(this);

        while (!st.empty()) {
            BTNode* n = st.top();
            st.pop();

            cout << n->val << " ";

            if (n->right) {
                st.push(n->right);
            }
            if (n->left) {
                st.push(n->left);
            }
        }
    }

    void inorder_stack() {
        stack<BTNode*> st;
        BTNode* cur = this;

        while (cur || !st.empty()) {
            while (cur) {
                st.push(cur);
                cur = cur->left;
            }
            cur = st.top();
            st.pop();

            cout << cur->val << " ";
            cur = cur->right;
        }
    }

    void postorder_stack() {
        stack<BTNode*> s1, s2;
        s1.push(this);

        while (!s1.empty()) {
            BTNode* n = s1.top();
            s1.pop();

            s2.push(n);

            if (n->left) {
                s1.push(n->left);
            }
            if (n->right) {
                s1.push(n->right);
            }
        }

        while (!s2.empty()) {
            cout << s2.top()->val << " ";
            s2.pop();
        }
    }

    void BFS() {
        queue<BTNode*> q;
        q.push(this);

        while (!q.empty()) {
            BTNode* n = q.front();
            q.pop();

            cout << n->val << " ";

            if (n->left) {
                q.push(n->left);
            }
            if (n->right) {
                q.push(n->right);
            }
        }
    }

    int sum() {
        int s = 0;
        queue<BTNode*> q;
        q.push(this);

        while (!q.empty()) {
            BTNode* n = q.front();
            q.pop();

            s += n->val;

            if (n->left) {
                q.push(n->left);
            }
            if (n->right) {
                q.push(n->right);
            }
        }

        return s;
    }
};

// ===================== BST NODE =====================
struct BSTNode {
    int val;
    BSTNode *left, *right;

    BSTNode(int v=0) : val(v), left(nullptr), right(nullptr) {}

    void insert(int value) {
        if (val == 0) {
            val = value;
            return;
        }

        if (value < val) {
            if (left) {
                left->insert(value);
            } else {
                left = new BSTNode(value);
            }
        } else {
            if (right) {
                right->insert(value);
            } else {
                right = new BSTNode(value);
            }
        }
    }

    BSTNode* find(int v) {
        if (v == val) {
            return this;
        }

        if (v < val) {
            if (left) {
                return left->find(v);
            }
            return nullptr;
        }

        if (right) {
            return right->find(v);
        }
        return nullptr;
    }

    void preorder() {
        cout << val << " ";
        if (left) {
            left->preorder();
        }
        if (right) {
            right->preorder();
        }
    }

    void inorder() {
        if (left) {
            left->inorder();
        }
        cout << val << " ";
        if (right) {
            right->inorder();
        }
    }

    void postorder() {
        if (left) {
            left->postorder();
        }
        if (right) {
            right->postorder();
        }
        cout << val << " ";
    }

    void preorder_stack() {
        stack<BSTNode*> st;
        st.push(this);

        while (!st.empty()) {
            BSTNode* n = st.top();
            st.pop();

            cout << n->val << " ";

            if (n->right) {
                st.push(n->right);
            }
            if (n->left) {
                st.push(n->left);
            }
        }
    }

    void inorder_stack() {
        stack<BSTNode*> st;
        BSTNode* cur = this;

        while (cur || !st.empty()) {
            while (cur) {
                st.push(cur);
                cur = cur->left;
            }
            cur = st.top();
            st.pop();

            cout << cur->val << " ";
            cur = cur->right;
        }
    }

    void postorder_stack() {
        stack<BSTNode*> s1, s2;
        s1.push(this);

        while (!s1.empty()) {
            BSTNode* n = s1.top();
            s1.pop();

            s2.push(n);

            if (n->left) {
                s1.push(n->left);
            }
            if (n->right) {
                s1.push(n->right);
            }
        }

        while (!s2.empty()) {
            cout << s2.top()->val << " ";
            s2.pop();
        }
    }

    void BFS() {
        queue<BSTNode*> q;
        q.push(this);

        while (!q.empty()) {
            BSTNode* n = q.front();
            q.pop();

            cout << n->val << " ";

            if (n->left) {
                q.push(n->left);
            }
            if (n->right) {
                q.push(n->right);
            }
        }
    }
};

// ===================== MAIN =====================
int main() {
    // BT
    BTNode* bt = new BTNode(10);
    int btValues[] = {5,20,3,7,15,30,1,6,8};
    for (int v : btValues) {
        bt->insert(v);
    }

    cout << "BT Preorder: ";
    bt->preorder();
    cout << "\n";

    cout << "BT Inorder: ";
    bt->inorder();
    cout << "\n";

    cout << "BT Postorder: ";
    bt->postorder();
    cout << "\n";

    cout << "BT BFS: ";
    bt->BFS();
    cout << "\n";

    cout << "Find 15: ";
    cout << (bt->find(15) ? "Found" : "Not Found") << "\n";

    cout << "BT Sum: ";
    cout << bt->sum() << "\n\n";

    // BST
    BSTNode* bst = new BSTNode(10);
    int bstValues[] = {1,5,20,3,7,15,30,6,8};
    for (int v : bstValues) {
        bst->insert(v);
    }

    cout << "BST Preorder: ";
    bst->preorder();
    cout << "\n";

    cout << "BST Inorder: ";
    bst->inorder();
    cout << "\n";

    cout << "BST Postorder: ";
    bst->postorder();
    cout << "\n";

    cout << "BST BFS: ";
    bst->BFS();
    cout << "\n";

    cout << "Find 7: ";
    cout << (bst->find(7) ? "Found" : "Not Found") << "\n";

    return 0;
}
