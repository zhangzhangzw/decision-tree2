# decision-tree2
my online code
from numpy import *
from math import log

import collections


print log(8, 2)
items = ['iPhone', 'kindle', 'kindle', 'new asin']


def inbound(po, fc):
    for asin in po:
        if asin in fc:
            fc[asin] += 1
        else:
            fc[asin] = 1


pek3 = {}
inbound(items, pek3)
print pek3


def outbound(po, fc):
    totalEntropy = 0
    for asin in fc:
        prob = float(fc[asin]) / len(po)
        entropy = - prob * log(prob, 2)
        totalEntropy += entropy
        print asin, prob, entropy

    return totalEntropy


def fastInbound(po):
    dic = collections.defaultdict(int)
    for asin in po:
        dic[asin] += 1
    return dic


tsn2 = fastInbound(items)
print tsn2

print outbound(items, pek3)
print len(items)
print inf
print e
