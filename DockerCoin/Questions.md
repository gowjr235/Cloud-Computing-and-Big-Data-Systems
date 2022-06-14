# Assignment-6 Questions

## Basic Information

Name: Jaehwan Lim

Student ID: 20380494

---

## (2 points) Report the performance of DockerCoins with different number of workers.

(1 point) TODO: Replace <FILL_IN> with the appropriate result.

| # of workers  | 1    | 2    | 3    | 4    | 5    | 10   |
| ------------- | ---- | ---- | ---- | ---- | ---- | ---- |
| hashes/second | 4    | 8    | 12   | 12   | 10   | 10   |

(1 point) When you have 10x workers, how much the performance is improved? Please describe the potential reasons for this phenomenon.

TODO: Compare to 1 worker, 10x workers speed up to 2.5 times from 4 hashes to 10 hashes. This is dues to a bottleneck component.

## (1 point) Detect latency and find the bottleneck component (rng or hasher).

(0.5 point) TODO: Replace <FILL_IN> with the appropriate result.

| Service      | Hasher | Rng  |
| ------------ | ------ | ---- |
| Average Latency (ms) | 0.9 | 721.8 |

(0.5 point) Which service is the bottleneck? 

TODO: Rng

## (1 point) Upload the screenshot of WebUI after setting up the hpa.

TODO: Save your screenshot as `webui_screenshot.png` and upload it.
![webui_screenshot](https://user-images.githubusercontent.com/90589037/144364485-b377ce47-8e60-4d09-b561-ce50b331faf9.png)

![](./webui_screenshot.png)

## (2 points) Open question: how to reduce the fluctuation of the HPA?

Apart from the autoscaling policy we provided, think about how to reduce the fluctuation of the HPA? Explain your method in details and show how you setup your own HPA.

TODO: Using flag --horizontal-pod-autoscaler-downscale-stabilization in the controller manager would smooth out the fluctuatin of the HPA which defaults to 5 minutes. This means that scaledowns will occur gradually, smoothing out the impact of rpidlt fluctuating metric values. The controller file is kube-controller-manager.yaml


