# GitHub Social Agent - Algorithm Guide

## How Matching Works
```
Profile Scan --> Repo Analysis --> Stack Extraction --> Similarity Score --> Recommendations
                    |                   |                     |
              Languages           Technologies          Jaccard Index
              Stars               Topics                Cosine Similarity
```

## Scoring Criteria
| Factor | Weight | Description |
|--------|--------|-------------|
| Language overlap | 30% | Shared programming languages |
| Topic match | 25% | Common repo topics/tags |
| Star patterns | 15% | Similar starring behavior |
| Activity level | 15% | Commit frequency similarity |
| Followback prediction | 15% | ML model for follow probability |

## ML Followback Prediction
- Features: mutual connections, repo similarity, activity overlap
- Model: Random Forest classifier
- Training: Historical follow/unfollow data

## Graph Traversal
- BFS through follower/following graph
- Depth limit: 2 hops
- Deduplication and scoring at each node