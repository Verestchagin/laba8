include <iostream>
include <string>
using namespace std;

struct Node{
	string data;
	Node *next;
};
struct List{
	Node *head;
};
bool reg_print(List list, string filter){
	bool test = false;
	List list1 = list;
	while(list1.head != nullptr){
		string str = list1.head->data;
		if(filter[0] == str[0]){
			for(int i = 0; i < filter.size(); i++){
				if(filter[i] != str[i]){
					test = false;
					break;
				}
				else{
					test = true;
				}
			}
			if(test == true){
				return true;
			}
		}
		list1.head = list1.head->next;
	}
	return false;
}
bool simple_print(List list, string = "str1"){
	List list1 = list;
	while(list1.head != nullptr){
		if(list1.head->data == filter){
			return true;
		}
		list1.head = list1.head->next;
	}
	return false;
}

int main(){
	List list;
	list.head = new Node{"str1", nullptr};
	list.head->next = new Node{"str2", nullptr};
	list.head->next->next = new Node {"str30", nullptr};
	cout << simple_print(list, "str1") << endl;
	cout << reg_print(list, "str300") << endl;
	
}
