---
title: Infer.NET と確率論的プログラミングでゲーム対戦リスト アプリを作成する
description: 確率論的プログラミングと Infer.NET を使用して、TrueSkill の簡易バージョンに基づいたゲーム対戦リスト アプリについて紹介します。
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 06538ec9de26f5aeabe474fbcae69f0a313c8d32
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679135"
---
# <a name="create-a-game-match-up-list-app-with-infernet-and-probabilistic-programming"></a><span data-ttu-id="aad50-103">Infer.NET と確率論的プログラミングでゲーム対戦リスト アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="aad50-103">Create a game match up list app with Infer.NET and probabilistic programming</span></span>

> [!NOTE]
> <span data-ttu-id="aad50-104">このトピックは現在プレビュー中の ML.NET について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="aad50-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="aad50-105">詳細については、[ML.NET の概要](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aad50-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="aad50-106">ここで説明する方法と関連サンプルでは、現時点では **ML.NET バージョン 0.10** が使用されています。</span><span class="sxs-lookup"><span data-stu-id="aad50-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="aad50-107">詳細については、リリース ノート ([GitHub リポジトリの dotnet/machinelearning ](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aad50-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="aad50-108">このハウツー ガイドでは、Infer.NET を使用した確率論的プログラミングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aad50-108">This how-to guide teaches you about probabilistic programming using Infer.NET.</span></span> <span data-ttu-id="aad50-109">確率論的プログラミングは、カスタム モデルがコンピューター プログラムとして表現される機械学習アプローチです。</span><span class="sxs-lookup"><span data-stu-id="aad50-109">Probabilistic programming is a machine learning approach where custom models are expressed as computer programs.</span></span> <span data-ttu-id="aad50-110">ドメインの知識をモデルに組み込み、機械学習システムから解釈可能にすることができます。</span><span class="sxs-lookup"><span data-stu-id="aad50-110">It allows for incorporating domain knowledge in the models and makes the machine learning system more interpretable.</span></span> <span data-ttu-id="aad50-111">また、新しいデータを取得したときの学習プロセスであるオンライン推論もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="aad50-111">It also supports online inference – the process of learning as new data arrives.</span></span> <span data-ttu-id="aad50-112">Infer.NET は、Microsoft で Azure、Xbox、Bing のさまざまな製品で使用されています。</span><span class="sxs-lookup"><span data-stu-id="aad50-112">Infer.NET is used in various products at Microsoft in Azure, Xbox, and Bing.</span></span>

## <a name="what-is-probabilistic-programming"></a><span data-ttu-id="aad50-113">確率論的プログラミングとは</span><span class="sxs-lookup"><span data-stu-id="aad50-113">What is probabilistic programming?</span></span>

<span data-ttu-id="aad50-114">確率論的プログラミングを使用すると、現実世界のプロセスの統計モデルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="aad50-114">Probabilistic programming allows you to create statistical models of real-world processes.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="aad50-115">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="aad50-115">Prerequisites</span></span>

- <span data-ttu-id="aad50-116">ローカルの開発環境の設定</span><span class="sxs-lookup"><span data-stu-id="aad50-116">Local development environment setup</span></span>

  <span data-ttu-id="aad50-117">このハウツー ガイドでは、開発用に使用できるマシンがあることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="aad50-117">This how-to guide expects you to have a machine you can use for development.</span></span> <span data-ttu-id="aad50-118">Mac、PC、または Linux 上でローカルの開発環境を設定する手順については、.NET の [10 分でわかる概要](https://www.microsoft.com/net/core)に関するチュートリアルに記載されています。</span><span class="sxs-lookup"><span data-stu-id="aad50-118">The .NET [Get Started in 10 minutes](https://www.microsoft.com/net/core) tutorial has instructions for setting up your local development environment on Mac, PC, or Linux.</span></span>

## <a name="create-your-app"></a><span data-ttu-id="aad50-119">アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="aad50-119">Create your app</span></span>

1. <span data-ttu-id="aad50-120">コマンド プロンプトを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aad50-120">Open a new command prompt and run the following commands:</span></span>

```console
dotnet new console -o myApp
cd myApp
```

<span data-ttu-id="aad50-121">`dotnet` コマンドで、種類が `console` の `new` アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="aad50-121">The `dotnet` command creates a `new` application of type `console`.</span></span> <span data-ttu-id="aad50-122">`-o` パラメーターで、アプリが格納されるディレクトリ `myApp` を作成し、必要なファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="aad50-122">The `-o` parameter creates a directory named `myApp` where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="aad50-123">`cd myApp` コマンドで、新しく作成されたアプリ ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="aad50-123">The `cd myApp` command puts you into the newly created app directory.</span></span>

## <a name="install-infernet-package"></a><span data-ttu-id="aad50-124">Infer.NET パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="aad50-124">Install Infer.NET package</span></span>

<span data-ttu-id="aad50-125">Infer.NET を使用するには、`Microsoft.ML.Probabilistic.Compiler` パッケージをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aad50-125">To use Infer.NET, you need to install the `Microsoft.ML.Probabilistic.Compiler` package.</span></span> <span data-ttu-id="aad50-126">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aad50-126">In your command prompt, run the following command:</span></span>

```console
dotnet add package Microsoft.ML.Probabilistic.Compiler
```

## <a name="design-your-model"></a><span data-ttu-id="aad50-127">モデルを設計する</span><span class="sxs-lookup"><span data-stu-id="aad50-127">Design your model</span></span>

<span data-ttu-id="aad50-128">このサンプルでは、オフィス内でプレイされる卓球またはフーズボールの試合を使用します。</span><span class="sxs-lookup"><span data-stu-id="aad50-128">The example sample uses table tennis or foosball matches played in the office.</span></span> <span data-ttu-id="aad50-129">参加者と各試合の結果があります。</span><span class="sxs-lookup"><span data-stu-id="aad50-129">You have the participants and outcome of each match.</span></span>  <span data-ttu-id="aad50-130">このデータからプレーヤーのスキルを推論します。</span><span class="sxs-lookup"><span data-stu-id="aad50-130">You want to infer the player's skills from this data.</span></span> <span data-ttu-id="aad50-131">各プレーヤーには正規分布の潜在的なスキルがあり、各試合の成績はこのスキルにノイズを加えたバージョンと仮定します。</span><span class="sxs-lookup"><span data-stu-id="aad50-131">Assume that each player has a normally distributed latent skill and their given match performance is a noisy version of this skill.</span></span> <span data-ttu-id="aad50-132">このデータによって、勝者の成績が敗者の成績よりも高くなるように制限します。</span><span class="sxs-lookup"><span data-stu-id="aad50-132">The data constrains the winner’s performance to be greater than the loser’s performance.</span></span> <span data-ttu-id="aad50-133">これは、一般的な [TrueSkill](https://www.microsoft.com/en-us/research/project/trueskill-ranking-system/) モデルの簡易バージョンです。TrueSkill モデルは、チーム、引き分けなどの拡張機能もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="aad50-133">This is a simplified version of the popular [TrueSkill](https://www.microsoft.com/en-us/research/project/trueskill-ranking-system/) model, which also supports teams, draws, and other extensions.</span></span> <span data-ttu-id="aad50-134">このモデルの[高度なバージョン](https://www.microsoft.com/en-us/research/publication/trueskill-2-improved-bayesian-skill-rating-system/)は、ベストセラーのゲーム タイトルである Halo と Gears of War のマッチメイキングに使用されています。</span><span class="sxs-lookup"><span data-stu-id="aad50-134">An [advanced version](https://www.microsoft.com/en-us/research/publication/trueskill-2-improved-bayesian-skill-rating-system/) of this model is used for matchmaking in the best-selling game titles Halo and Gears of War.</span></span>

<span data-ttu-id="aad50-135">推定されたプレーヤーのスキルをその分散 (そのスキルの不確実性の尺度) と共に列挙する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aad50-135">You need to list the inferred player skills, alongside with their variance – the measure of uncertainty around the skills.</span></span>

<span data-ttu-id="aad50-136">*ゲーム結果のサンプル データ*</span><span class="sxs-lookup"><span data-stu-id="aad50-136">*Game result sample data*</span></span>

<span data-ttu-id="aad50-137">ゲーム</span><span class="sxs-lookup"><span data-stu-id="aad50-137">Game</span></span> |<span data-ttu-id="aad50-138">勝者</span><span class="sxs-lookup"><span data-stu-id="aad50-138">Winner</span></span> | <span data-ttu-id="aad50-139">敗者</span><span class="sxs-lookup"><span data-stu-id="aad50-139">Loser</span></span>
---------|----------|---------
 <span data-ttu-id="aad50-140">1</span><span class="sxs-lookup"><span data-stu-id="aad50-140">1</span></span> | <span data-ttu-id="aad50-141">プレーヤー 0</span><span class="sxs-lookup"><span data-stu-id="aad50-141">Player 0</span></span> | <span data-ttu-id="aad50-142">プレーヤー 1</span><span class="sxs-lookup"><span data-stu-id="aad50-142">Player 1</span></span>
 <span data-ttu-id="aad50-143">2</span><span class="sxs-lookup"><span data-stu-id="aad50-143">2</span></span> | <span data-ttu-id="aad50-144">プレーヤー 0</span><span class="sxs-lookup"><span data-stu-id="aad50-144">Player 0</span></span> | <span data-ttu-id="aad50-145">プレーヤー 3</span><span class="sxs-lookup"><span data-stu-id="aad50-145">Player 3</span></span>
 <span data-ttu-id="aad50-146">3</span><span class="sxs-lookup"><span data-stu-id="aad50-146">3</span></span> | <span data-ttu-id="aad50-147">プレーヤー 0</span><span class="sxs-lookup"><span data-stu-id="aad50-147">Player 0</span></span> | <span data-ttu-id="aad50-148">プレーヤー 4</span><span class="sxs-lookup"><span data-stu-id="aad50-148">Player 4</span></span>
 <span data-ttu-id="aad50-149">4</span><span class="sxs-lookup"><span data-stu-id="aad50-149">4</span></span> | <span data-ttu-id="aad50-150">プレーヤー 1</span><span class="sxs-lookup"><span data-stu-id="aad50-150">Player 1</span></span> | <span data-ttu-id="aad50-151">プレーヤー 2</span><span class="sxs-lookup"><span data-stu-id="aad50-151">Player 2</span></span>
 <span data-ttu-id="aad50-152">5</span><span class="sxs-lookup"><span data-stu-id="aad50-152">5</span></span> | <span data-ttu-id="aad50-153">プレーヤー 3</span><span class="sxs-lookup"><span data-stu-id="aad50-153">Player 3</span></span> | <span data-ttu-id="aad50-154">プレーヤー 1</span><span class="sxs-lookup"><span data-stu-id="aad50-154">Player 1</span></span>
 <span data-ttu-id="aad50-155">6</span><span class="sxs-lookup"><span data-stu-id="aad50-155">6</span></span> | <span data-ttu-id="aad50-156">プレーヤー 4</span><span class="sxs-lookup"><span data-stu-id="aad50-156">Player 4</span></span> | <span data-ttu-id="aad50-157">プレーヤー 2</span><span class="sxs-lookup"><span data-stu-id="aad50-157">Player 2</span></span>

<span data-ttu-id="aad50-158">サンプル データを詳しく見ると、プレーヤー 3 とプレーヤー 4 のどちらも 1 勝 1 敗であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="aad50-158">With a closer look at the sample data, you’ll notice that players 3 and 4 both have one win and one loss.</span></span> <span data-ttu-id="aad50-159">確率論的プログラミングを使用するとランキングがどのようになるかを見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="aad50-159">Let's see what the rankings look like using probabilistic programming.</span></span> <span data-ttu-id="aad50-160">オフィスの対戦リストであっても開発者にとってはゼロベースなので、プレーヤーがゼロである点にも注意してください。</span><span class="sxs-lookup"><span data-stu-id="aad50-160">Notice also there is a player zero because even office match up lists are zero based to us developers.</span></span>

## <a name="write-some-code"></a><span data-ttu-id="aad50-161">コードを記述する</span><span class="sxs-lookup"><span data-stu-id="aad50-161">Write some code</span></span>

<span data-ttu-id="aad50-162">モデルを設計したら、次は Infer.NET モデル API を使用して確率論的プログラムとして表現します。</span><span class="sxs-lookup"><span data-stu-id="aad50-162">Having designed the model, it’s time to express it as a probabilistic program using the Infer.NET modeling API.</span></span> <span data-ttu-id="aad50-163">使い慣れたテキスト エディターで `Program.cs` を開き、すべての内容を次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="aad50-163">Open `Program.cs` in your favorite text editor and replace all of its contents with the following code:</span></span>

```csharp
namespace myApp

{
    using System;
    using System.Linq;
    using Microsoft.ML.Probabilistic;
    using Microsoft.ML.Probabilistic.Distributions;
    using Microsoft.ML.Probabilistic.Models;

    class Program
    {

        static void Main(string[] args)
        {
            // The winner and loser in each of 6 samples games
            var winnerData = new[] { 0, 0, 0, 1, 3, 4 };
            var loserData = new[] { 1, 3, 4, 2, 1, 2 };

            // Define the statistical model as a probabilistic program
            var game = new Range(winnerData.Length);
            var player = new Range(winnerData.Concat(loserData).Max() + 1);
            var playerSkills = Variable.Array<double>(player);
            playerSkills[player] = Variable.GaussianFromMeanAndVariance(6, 9).ForEach(player);

            var winners = Variable.Array<int>(game);
            var losers = Variable.Array<int>(game);

            using (Variable.ForEach(game))
            {
                // The player performance is a noisy version of their skill
                var winnerPerformance = Variable.GaussianFromMeanAndVariance(playerSkills[winners[game]], 1.0);
                var loserPerformance = Variable.GaussianFromMeanAndVariance(playerSkills[losers[game]], 1.0);

                // The winner performed better in this game
                Variable.ConstrainTrue(winnerPerformance > loserPerformance);
            }

            // Attach the data to the model
            winners.ObservedValue = winnerData;
            losers.ObservedValue = loserData;

            // Run inference
            var inferenceEngine = new InferenceEngine();
            var inferredSkills = inferenceEngine.Infer<Gaussian[]>(playerSkills);

            // The inferred skills are uncertain, which is captured in their variance
            var orderedPlayerSkills = inferredSkills
               .Select((s, i) => new { Player = i, Skill = s })
               .OrderByDescending(ps => ps.Skill.GetMean());

            foreach (var playerSkill in orderedPlayerSkills)
            {
                Console.WriteLine($"Player {playerSkill.Player} skill: {playerSkill.Skill}");
            }
        }
    }
}
```

## <a name="run-your-app"></a><span data-ttu-id="aad50-164">アプリの実行</span><span class="sxs-lookup"><span data-stu-id="aad50-164">Run your app</span></span>

<span data-ttu-id="aad50-165">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aad50-165">In your command prompt, run the following command:</span></span>

```console
dotnet run
```

## <a name="results"></a><span data-ttu-id="aad50-166">結果</span><span class="sxs-lookup"><span data-stu-id="aad50-166">Results</span></span>

<span data-ttu-id="aad50-167">結果は以下のようになるはずです。</span><span class="sxs-lookup"><span data-stu-id="aad50-167">Your results should be similar to the following:</span></span>

```
Compiling model...done.
Iterating:
.........|.........|.........|.........|.........| 50
Player 0 skill: Gaussian(9.517, 3.926)
Player 3 skill: Gaussian(6.834, 3.892)
Player 4 skill: Gaussian(6.054, 4.731)
Player 1 skill: Gaussian(4.955, 3.503)
Player 2 skill: Gaussian(2.639, 4.288)
```

<span data-ttu-id="aad50-168">この結果では、モデルに従ってプレーヤー 3 がプレーヤー 4 よりわずかにランクが高い点に注目してください。</span><span class="sxs-lookup"><span data-stu-id="aad50-168">In the results, notice that player 3 ranks slightly higher than player 4 according to our model.</span></span> <span data-ttu-id="aad50-169">これは、プレーヤー 3 がプレーヤー 1 に勝ったことが、プレーヤー 4 がプレーヤー 2 に勝ったことよりも重要であるためです (プレーヤー 1 がプレーヤー 2 に勝つことに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="aad50-169">That’s because the victory of player 3 over player 1 is more significant than the victory of player 4 over player 2 – note that player 1 beats player 2.</span></span> <span data-ttu-id="aad50-170">プレーヤー 0 が全体のチャンピオンです。</span><span class="sxs-lookup"><span data-stu-id="aad50-170">Player 0 is the overall champ!</span></span>

## <a name="keep-learning"></a><span data-ttu-id="aad50-171">学習の継続</span><span class="sxs-lookup"><span data-stu-id="aad50-171">Keep learning</span></span>

<span data-ttu-id="aad50-172">統計モデルの設計は独自のスキルです。</span><span class="sxs-lookup"><span data-stu-id="aad50-172">Designing statistical models is a skill on its own.</span></span> <span data-ttu-id="aad50-173">Microsoft Research Cambridge チームは、この記事を簡単に紹介した[無料のオンライン ブック](http://mbmlbook.com/)を作成しました。</span><span class="sxs-lookup"><span data-stu-id="aad50-173">The Microsoft Research Cambridge team has written a [free online book](http://mbmlbook.com/), which gives a gentle introduction to the article.</span></span> <span data-ttu-id="aad50-174">このブックの第 3 章には、TrueSkill モデルが詳しく説明されています。</span><span class="sxs-lookup"><span data-stu-id="aad50-174">Chapter 3 of this book covers the TrueSkill model in more detail.</span></span> <span data-ttu-id="aad50-175">モデルを考えついたら、Infer.NET Web サイトの[膨大なドキュメント](https://dotnet.github.io/infer/)を使用してモデルをコードに変換することができます。</span><span class="sxs-lookup"><span data-stu-id="aad50-175">Once you have a model in mind, you can transform it into code using the [extensive documentation](https://dotnet.github.io/infer/) on the Infer.NET website.</span></span>

## <a name="next-steps"></a><span data-ttu-id="aad50-176">次の手順</span><span class="sxs-lookup"><span data-stu-id="aad50-176">Next steps</span></span>

<span data-ttu-id="aad50-177">学習を続けてその他のサンプルを確認するには、Infer.NET の GitHub リポジトリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aad50-177">Check out the Infer.NET GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="aad50-178">dotnet/infer の GitHub リポジトリ</span><span class="sxs-lookup"><span data-stu-id="aad50-178">dotnet/infer GitHub repository</span></span>](https://github.com/dotnet/infer)
