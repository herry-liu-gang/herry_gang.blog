---
layout: post
title: "R语言学习“基于cs50R”的记录 1 "
date: 2024-10-07 12:00:00 +0800
categories: blog update
---

# **Representing data**
    `-file.creat("hello.R")  /创建一个R文件`
    `-ctrl+l  /清空控制台`
    `-print("hello,world")`
    `-readline("what's your name?")  /读取用户输入`
    `-name <- readline("what's your name?")  /返回赋值给name`
    `-greeting <- paste("Hello,",name,sep = "")   /将字符串连接。并且通过令 sep ="" 使得连接部位没有空格`
    /-或者使用 greeting <- paste0("Hello, ",name)   /直接无缝连接

```    -a,b,c 
        a <- as.integer(a)
        ...
        ...
        total <- a+b+c
        >简化为：
            total <- sum(a,b,c) 
```
## **读取表格**
    ```-votes <- read.table(
        "votes.csv"
        sep = ","
        header = TRUE
        )```
    `-View(votes)`
    `votes <- read.csv("") 是更快的方式`
    `votes[row,column]`

## **向量**
    ``` colnames(votes)    /显示存在的列名
        votes$candidate    /show the column of candidate
        ...
        ...
        sum(votes$poll[1], votes$poll[2], votes$poll[3])
        sum(votes$poll)
    ```
## **vector arithmetic**
    `votes$total <- votes$poll +votes$mail `
    `write.csv(votes,"total.csv",row.names =FALSE ) `

## **USE other's data**
    ```url <- "https://github.com/fivethirtyeight/data/raw/master/non-voters/nonvoters_data.csv"
       voters <- read.csv(url)
       nrow(voters)
       ncol(voters)  /determine how many rows and columns exist in it 
       unique(voters$voter_category)    /return the unique value

       ```
## **special values**
    ```
    NA表示“不可用”,Inf、-Inf、NaN和NULL。它们分别表示无限、负无限、非数字和空值（或无）
    ```

## **factor**
```
factor(
  voters$Q21,
  labels = c("?", "Yes", "No", "Unsure/Undecided")
)
```
    /show the special levels of data in q21,and labels are applied to each level.
```
 voters$Q21 <- factor(
  voters$Q21,
  labels = c("Yes", "No", "Unsure/Undecided"),
  exclude = c(-1)
)
```
    /extra exclude -1 ,

## **see you next time**

    























