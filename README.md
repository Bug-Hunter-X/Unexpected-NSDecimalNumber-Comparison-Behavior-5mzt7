# Objective-C NSDecimalNumber Comparison Issue

This repository demonstrates a common, yet subtle, error when comparing `NSDecimalNumber` objects in Objective-C.  The problem stems from the misuse of the `==` operator for equality checks.  Instead, the `compare:` method should always be used.

## The Problem

The `==` operator in Objective-C checks for pointer equality, not value equality. Two `NSDecimalNumber` objects can represent the same numerical value but have different memory addresses, thus resulting in `false` when compared with `==`.

## The Solution

Use the `compare:` method of `NSDecimalNumber` to accurately compare values for equality (or other ordering).