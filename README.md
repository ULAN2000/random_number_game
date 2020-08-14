/* ############### Random number generator game ob=n C++ language ##################
#                      This game - for programmers                                 #
#                          Language: Russian                                       #
#                            Version 1.0                                           #
#                   for windows system("cls") - command                            #
#                 2020.08.14  Ulan's softwares Copyright                           #
####################################################################################
*/
#include <iostream>
#include <thread>
using namespace std;

int x_rand, user1_rate = 0, user2_rate = 0;
int num_generator_begin, num_generator_end, n_iteration;
int user1_num, user1_num2, user1_num3, user2_num, user2_num2, user2_num3;
string user1_name, user2_name;

void computer(){
    cout<<"Введите вашу имю: ";
    cin>>user1_name;
    system("clear");
    cout<<"Введите начало диапазона числа: ";
    cin>>num_generator_begin;
    system("clear");
    cout<<"Введите конец диапазона числа: ";
    cin>>num_generator_end;
    while(num_generator_begin>num_generator_end || num_generator_begin == num_generator_end){
        cout<<"Ошибка!"<<endl;
        cout<<"Начальный диапазон числа, не должно быть равно или меньше конца диапазона числа"<<endl;
        cout<<"Введите начало диапазона числа: ";
        cin>>num_generator_begin;
        system("clear");
        cout<<"Введите конец диапазона числа: ";
        cin>>num_generator_end;
    }
    system("clear");
    cout<<"Введите количество итерации случайных чисел: ";
    cin>>n_iteration;
    cout<<user1_name<<", введите 3 числа от "<<num_generator_begin<<" до "<<num_generator_end<<endl;
    cout<<"Число 1: ";cin>>user1_num;

    while(user1_num > num_generator_end || user1_num < num_generator_begin){
        cout<<"Ошибка!\nВведите числа в диапазоне от "<<num_generator_begin<<" до "<<num_generator_end<<endl;
        cin>>user1_num;
    }

    cout<<"Число 2: ";cin>>user1_num2;
    while(user1_num2 > num_generator_end || user1_num2 < num_generator_begin){
        cout<<"Ошибка!\nВведите числа в диапазоне от "<<num_generator_begin<<" до "<<num_generator_end<<endl;
        cin>>user1_num2;
    }

    cout<<"Число 3: ";cin>>user1_num3;
    while(user1_num3 > num_generator_end || user1_num3 < num_generator_begin){
        cout<<"Ошибка!\nВведите числа в диапазоне от "<<num_generator_begin<<" до "<<num_generator_end<<endl;
        cin>>user1_num3;
    }


        cout<<"--Computer--"<<endl;
        user2_num = num_generator_begin+rand()%num_generator_end;
        user2_num2 = num_generator_begin+rand()%num_generator_end;
        user2_num3 = num_generator_begin+rand()%num_generator_end;
        cout<<"Число 1: "<<user2_num<<endl;
        this_thread::sleep_for(1s);
        cout<<"Число 2: "<<user2_num2<<endl;
        this_thread::sleep_for(1s);
        cout<<"Число 3: "<<user2_num3<<endl;
        this_thread::sleep_for(1s);


    system("clear");
    for(int i = 1; i <= n_iteration; i++){
        x_rand = num_generator_begin+rand()%num_generator_end;
        cout<<"Итерация: "<<i<<endl;
        this_thread::sleep_for(1s);
        cout<<"Случайное число: "<<x_rand<<endl;
        

        //-----User 1's Condition-----//
        if(x_rand==user1_num){
            cout<<user1_name<<", совпало число: "<<user1_num<<endl;
            user1_rate+=1;
            this_thread::sleep_for(0.7s);
        }if(x_rand==user1_num2){
            cout<<user1_name<<", совпало: "<<user1_num2<<endl;
            user1_rate+=1;
            this_thread::sleep_for(0.7s);
        }if(x_rand==user1_num3){
            cout<<user1_name<<", совпало число: "<<user1_num3<<endl;
            user1_rate+=1;
            this_thread::sleep_for(0.5s);
        }
        //-----END - User 1's Condition-----//


        //-----User 2's Condition-----//
        if(x_rand==user2_num){
           cout<<"Computer, совпало число: "<<user2_num<<endl;
           user2_rate+=1;
           this_thread::sleep_for(0.5s); 
        }if(x_rand==user2_num2){
            cout<<"Computer , совпало число: "<<user2_num2<<endl;
            user2_rate+=1;
            this_thread::sleep_for(0.5s);
        }if(x_rand==user2_num3){
            cout<<"Computer, совпало число: "<<user2_num3<<endl;
            user2_rate+=1;
            this_thread::sleep_for(0.5s);
        }
        //-----END - User 2's Condition-----//
    }cout<<"|---Баллы---|"<<endl;
    cout<<user1_name<<": "<<user1_rate<<endl;
    cout<<"Computer: "<<user2_rate<<endl;
    if(user1_rate == user2_rate){
        cout<<"Ничья"<<endl;
    }else if(user1_rate > user2_rate){
        cout<<"Победитель: "<<user1_name<<endl;
    }else if(user2_rate > user1_rate){
        cout<<"Победитель: Computer"<<endl;
    }
}

void human(){
    cout<<"Имя 1 игрока: ";
    cin>>user1_name;
    system("clear");
    cout<<"Имя 2 игрока: ";
    cin>>user2_name;
    system("clear");
    cout<<"Введите начало диапазона числа для генерации: ";
    cin>>num_generator_begin;
    system("clear");
    cout<<"Введите конец диапазона числа для генерации: ";
    cin>>num_generator_end;
     while(num_generator_begin>num_generator_end || num_generator_begin == num_generator_end){
        cout<<"Ошибка!"<<endl;
        cout<<"Начальный диапазон числа, не должно быть равно или меньше конца диапазона числа"<<endl;
        cout<<"Введите начало диапазона числа: ";
        cin>>num_generator_begin;
        system("clear");
        cout<<"Введите конец диапазона числа: ";
        cin>>num_generator_end;
    }
    system("clear");
    cout<<"Введите количество итерации случайных чисел: ";
    cin>>n_iteration;
    


    //-----------------------While Loop Logoc Block 1-----------------------//
    cout<<user1_name<<", введите 3 числа от "<<num_generator_begin<<" до "<<num_generator_end<<endl;
    cout<<"Число 1: ";cin>>user1_num;
    while(user1_num > num_generator_end || user1_num < num_generator_begin){
        cout<<"Ошибка!\nВведите числа в диапазоне от "<<num_generator_begin<<" до "<<num_generator_end<<endl;
        cin>>user1_num;
    }

    cout<<"Число 2: ";cin>>user1_num2;
    while(user1_num2 > num_generator_end || user1_num2 < num_generator_begin){
        cout<<"Ошибка!\nВведите числа в диапазоне от "<<num_generator_begin<<" до "<<num_generator_end<<endl;
        cin>>user1_num2;
    }

    cout<<"Число 3: ";cin>>user1_num3;
    while(user1_num3 > num_generator_end || user1_num3 < num_generator_begin){
        cout<<"Ошибка!\nВведите числа в диапазоне от "<<num_generator_begin<<" до "<<num_generator_end<<endl;
        cin>>user1_num3;
    }
    //-----------------------END - While Loop Logic Block 1-----------------------//





    //-----------------------While Loop Logic Block 2-----------------------//
    cout<<user2_name<<", введите 3 числа от "<<num_generator_begin<<" до "<<num_generator_end<<endl;
    cout<<"Число 1: ";cin>>user2_num;
    while(user2_num > num_generator_end || user2_num < num_generator_begin){
        cout<<"Ошибка!\nВведите числа в диапазоне от "<<num_generator_begin<<" до "<<num_generator_end<<endl;
        cin>>user2_num;
    }

    cout<<"Число 2: ";cin>>user2_num2;
     while(user2_num2 > num_generator_end || user2_num2 < num_generator_begin){
        cout<<"Ошибка!\nВведите числа в диапазоне от "<<num_generator_begin<<" до "<<num_generator_end<<endl;
        cin>>user2_num2;
    }

    cout<<"Число 3: ";cin>>user2_num3;
    while(user2_num3 > num_generator_end || user2_num3 < num_generator_begin){
        cout<<"Ошибка!\nВведите числа в диапазоне от "<<num_generator_begin<<" до "<<num_generator_end<<endl;
        cin>>user2_num3;
    }
    //-----------------------END - While Loop Logic Block 2-----------------------//



    system("clear");
    for(int i = 1; i <= n_iteration; i++){
        x_rand = num_generator_begin+rand()%num_generator_end;
        cout<<"Итерация: "<<i<<endl;
        this_thread::sleep_for(1s);
        cout<<"Случайное число: "<<x_rand<<endl;
        

        //-----User 1's Condition-----//
        if(x_rand==user1_num){
            cout<<user1_name<<", совпало число: "<<user1_num<<endl;
            user1_rate+=1;
            this_thread::sleep_for(0.7s);
        }if(x_rand==user1_num2){
            cout<<user2_name<<", совпало: "<<user1_num2<<endl;
            user1_rate+=1;
            this_thread::sleep_for(0.7s);
        }if(x_rand==user1_num3){
            cout<<user2_name<<", совпало число: "<<user1_num3<<endl;
            user1_rate+=1;
            this_thread::sleep_for(0.5s);
        }
        //-----END - User 1's Condition-----//


        //-----User 2's Condition-----//
        if(x_rand==user2_num){
           cout<<user2_name<<", совпало число: "<<user2_num<<endl;
           user2_rate+=1;
           this_thread::sleep_for(0.5s); 
        }if(x_rand==user2_num2){
            cout<<user2_name<<", совпало число: "<<user2_num2<<endl;
            user2_rate+=1;
            this_thread::sleep_for(0.5s);
        }if(x_rand==user2_num3){
            cout<<user2_name<<", совпало число: "<<user2_num3<<endl;
            user2_rate+=1;
            this_thread::sleep_for(0.5s);
        }
        //-----END - User 2's Condition-----//

    }cout<<"|---Баллы---|"<<endl;
    cout<<user1_name<<" :"<<user1_rate<<endl;
    cout<<user2_name<<" :"<<user2_rate<<endl;
    if(user1_rate == user2_rate){
        cout<<"Ничья"<<endl;
    }else if(user1_rate > user2_rate){
        cout<<"Победитель: "<<user1_name<<endl;
    }else if(user2_rate > user1_rate){
        cout<<"Победитель: "<<user2_name<<endl;
    }

}

void run_game(){
    char select_c_h;
    cout<<"------------------------------------------------------------------------------"<<endl;
    cout<<"| Игра - Генератор случайных чисел | версия: 1.0 | Ulan's software copyright |"<<endl;
    cout<<"| Нажимте на 'ввод(enter)' чтобы играть                                      |"<<endl;
    cout<<"------------------------------------------------------------------------------"<<endl;
    cin.get();
    cout<<"Против кого хотите сыграть? ";
    cout<<"C - компьютер\nH - человек ";
    cin>>select_c_h;
    if(select_c_h=='H' || select_c_h=='h'){
        human();
    }else if(select_c_h=='C' || select_c_h=='c'){
        computer();
    }   
}

int main(){
    srand(time(0));
    run_game();
    return 0;
}
