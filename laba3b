#include <iostream> 
#include <vector> 

class Detail {
protected:
    Detail() {}
public:
    virtual ~Detail() {}
    template<typename T>
    friend void add_to_vector(std::vector<Detail*>& v);
};

class Build : public Detail {
protected:
    Build() = default;
public:
    virtual ~Build() {}
    template<typename T>
    friend void add_to_vector(std::vector<Detail*>& v);
};

template<typename T>
void add_to_vector(std::vector<Detail*>& v) {
    v.push_back(new T());
}

int main() {
    std::vector<Detail*> Details;
    add_to_vector<Detail>(Details);
    add_to_vector<Build>(Details);
    add_to_vector<Detail>(Details);
    add_to_vector<Build>(Details);

    for (auto d : Details) {
        delete d;
    }
    Details.clear();

    return 0;
}
