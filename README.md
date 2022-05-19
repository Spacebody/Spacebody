```rust
impl Spacebody {
    pub fn introduce() -> Spacebody {
        Spacebody {
            name: "Jerry",
            sex: "Male",
            location: Location {
                city: "Hangzhou",
                country: "China",
            },
            profession: "BackEnd",
            emails: vec!["510662916@qq.com", "jerryzyl18@gmail.com"],
            blog: "https://blog.yilin.dev",
            skills: vec!["Spring/SpringBoot", "Microservices", "Docker"],
            languages: vec!["Java", "C/C++", "Rust"],
            hobbies: vec!["Reading", "Photography"],
            status: vec![Status::BusyForWork, Status::EnjoyHolidays, Status::SeekTrueLove].choose(&mut rand::thread_rng()).unwrap().clone(),
        }
    }
}

#[derive(Debug)]
pub struct Spacebody {
    name: &'static str,
    sex: &'static str,
    location: Location,
    profession: &'static str,
    emails: Vec<&'static str>,
    blog: &'static str,
    skills: Vec<&'static str>,
    languages: Vec<&'static str>,
    hobbies: Vec<&'static str>,
    status: Status,
}

#[derive(Debug, Copy, Clone)]
enum Status {
    BusyForWork, 
    EnjoyHolidays,
    SeekTrueLove,
}

#[derive(Debug)]
struct Location {
    city: &'static str,
    country: &'static str
}

use rand::seq::SliceRandom;
```
