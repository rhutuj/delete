# delete





node *del(node *root, string k)
    {
        node *temp;

        if (root == NULL)
        {
            cout << "\nElement Not Found";
            return root;
        }

        if (k < root->k)
        {
            root->left = del(root->left, k);
            return root;
        }
        if (k > root->k)
        {
            root->right = del(root->right, k);
            return root;
        }

        if (root->right == NULL && root->left == NULL)
        {
            temp = root;
            delete temp;
            return NULL;
        }
        if (root->right == NULL)
        {
            temp = root;
            root = root->left;
            delete temp;
            return root;
        }
        else if (root->left == NULL)

        {
            temp = root;
            root = root->right;
            delete temp;
            return root;
        }
        temp = min(root->right);
        root->k = temp->k;
        root->right = del(root->right, temp->k);
        return root;
    }

    node *min(node *q)
    {
        while (q->left != NULL)

        {
            q = q->left;
        }
        return q;
    }
    node *get_root()
    {
        return root;
    }
