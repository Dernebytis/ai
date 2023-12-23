# ai
Ai
class DecisionTree:
    def __init__(self):
        self.tree = self.build_tree()

    def build_tree(self):
        # This is a simple decision tree representing a binary decision
        tree = {
            'question': 'Is it raining?',
            'yes_branch': {
                'question': 'Do you have an umbrella?',
                'yes_branch': 'Go outside',
                'no_branch': 'Wait for the rain to stop'
            },
            'no_branch': 'Go outside'
        }
        return tree

    def make_decision(self, input_data):
        current_node = self.tree
        while 'question' in current_node:
            question = current_node['question']
            answer = input(f"{question} (yes/no): ")
            current_node = current_node['yes_branch'] if answer.lower() == 'yes' else current_node['no_branch']

        return current_node

# Example usage
decision_tree = DecisionTree()
result = decision_tree.make_decision({})
print(result)
