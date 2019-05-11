# NSTimer_objectiveC
NSTimer_objectiveC

``` objective-c
//
//  ViewController.m
//  StoringInformationInTheTimer
//
//  Created by Carlos Santiago Cruz on 5/11/19.
//  Copyright © 2019 Carlos Santiago Cruz. All rights reserved.
//

#import "ViewController.h"

@interface ViewController ()

@end

@implementation ViewController

- (void)viewDidLoad {
    [super viewDidLoad];
    
    NSDictionary *dictionary = @{
                                 @"Message":@"Hello, World!",
                                 @"anotherMessage":@"This is another Hello World"
                                 };
    [NSTimer scheduledTimerWithTimeInterval:5.0
                                     target:self
                                   selector:@selector(doSomething:)
                                   userInfo:dictionary
                                    repeats:NO];
    
    [NSTimer scheduledTimerWithTimeInterval:3.0
                                     target:self
                                   selector:@selector(doSomethingElse:)
                                   userInfo:dictionary
                                    repeats:YES];
}

- (void)doSomething:(NSTimer *)timer
{
    NSLog(@"%@", timer.userInfo[@"Message"]);
}

- (void)doSomethingElse:(NSTimer *)timer
{
    NSLog(@"%@", timer.userInfo[@"anotherMessage"]);
}

@end
```



