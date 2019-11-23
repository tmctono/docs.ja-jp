---
title: フォームと検証
description: Blazor でクライアント側の検証を使用してフォームを構築する方法について説明します。
author: danroth27
ms.author: daroth
ms.date: 09/19/2019
ms.openlocfilehash: c30db5e06d36a6d15301835fe782b21058a80592
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841955"
---
# <a name="forms-and-validation"></a><span data-ttu-id="dd7cc-103">フォームと検証</span><span class="sxs-lookup"><span data-stu-id="dd7cc-103">Forms and validation</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="dd7cc-104">ASP.NET Web Forms framework には、フォーム (`RequiredFieldValidator`、`CompareValidator`、`RangeValidator`など) に入力されたユーザー入力の検証を処理する一連の検証サーバーコントロールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-104">The ASP.NET Web Forms framework includes a set of validation server controls that handle validating user input entered into a form (`RequiredFieldValidator`, `CompareValidator`, `RangeValidator`, and so on).</span></span> <span data-ttu-id="dd7cc-105">ASP.NET Web Forms framework は、データ注釈 (`[Required]`、`[StringLength]`、`[Range]`など) に基づいてモデルをバインドし、モデルを検証することもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-105">The ASP.NET Web Forms framework also supports model binding and validating the model based on data annotations (`[Required]`, `[StringLength]`, `[Range]`, and so on).</span></span> <span data-ttu-id="dd7cc-106">検証ロジックは、控えめな JavaScript ベースの検証を使用して、サーバーとクライアントの両方に適用できます。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-106">The validation logic can be enforced both on the server and on the client using unobtrusive JavaScript-based validation.</span></span> <span data-ttu-id="dd7cc-107">`ValidationSummary` サーバーコントロールは、検証エラーの概要をユーザーに表示するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-107">The `ValidationSummary` server control is used to display a summary of the validation errors to the user.</span></span>

<span data-ttu-id="dd7cc-108">Blazor は、クライアントとサーバーの間の検証ロジックの共有をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-108">Blazor supports the sharing of validation logic between both the client and the server.</span></span> <span data-ttu-id="dd7cc-109">ASP.NET には、多くの一般的なサーバー検証の事前構築済みの JavaScript 実装が用意されています。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-109">ASP.NET provides pre-built JavaScript implementations of many common server validations.</span></span> <span data-ttu-id="dd7cc-110">多くの場合、開発者は、アプリ固有の検証ロジックを完全に実装するために JavaScript を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-110">In many cases, the developer still has to write JavaScript to fully implement their app-specific validation logic.</span></span> <span data-ttu-id="dd7cc-111">サーバーとクライアントの両方で、同じモデル型、データ注釈、および検証ロジックを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-111">The same model types, data annotations, and validation logic can be used on both the server and client.</span></span>

<span data-ttu-id="dd7cc-112">Blazor には、一連の入力コンポーネントが用意されています。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-112">Blazor provides a set of input components.</span></span> <span data-ttu-id="dd7cc-113">入力コンポーネントは、モデルへのフィールドデータのバインドを処理し、フォームが送信されたときにユーザー入力を検証します。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-113">The input components handle binding field data to a model and validating the user input when the form is submitted.</span></span>

|<span data-ttu-id="dd7cc-114">入力コンポーネント</span><span class="sxs-lookup"><span data-stu-id="dd7cc-114">Input component</span></span>|<span data-ttu-id="dd7cc-115">レンダリングされた HTML 要素</span><span class="sxs-lookup"><span data-stu-id="dd7cc-115">Rendered HTML element</span></span>    |
|---------------|-------------------------|
|`InputCheckbox`|`<input type="checkbox">`|
|`InputDate`    |`<input type="date">`    |
|`InputNumber`  |`<input type="number">`  |
|`InputSelect`  |`<select>`               |
|`InputText`    |`<input>`                |
|`InputTextArea`|`<textarea>`             |

<span data-ttu-id="dd7cc-116">`EditForm` コンポーネントは、これらの入力コンポーネントをラップし、`EditContext`を使用して検証プロセスを調整します。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-116">The `EditForm` component wraps these input components and orchestrates the validation process through an `EditContext`.</span></span> <span data-ttu-id="dd7cc-117">`EditForm`を作成するときは、`Model` パラメーターを使用して、バインドするモデルインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-117">When creating an `EditForm`, you specify what model instance to bind to using the `Model` parameter.</span></span> <span data-ttu-id="dd7cc-118">通常、検証はデータ注釈を使用して行われ、拡張可能です。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-118">Validation is typically done using data annotations, and it's extensible.</span></span> <span data-ttu-id="dd7cc-119">データ注釈に基づく検証を有効にするには、`EditForm`の子として `DataAnnotationsValidator` コンポーネントを追加します。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-119">To enable data annotation-based validation, add the `DataAnnotationsValidator` component as a child of the `EditForm`.</span></span> <span data-ttu-id="dd7cc-120">`EditForm` コンポーネントには、有効な (`OnValidSubmit`) および無効な (`OnInvalidSubmit`) 送信を処理するための便利なイベントが用意されています。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-120">The `EditForm` component provides a convenient event for handling valid (`OnValidSubmit`) and invalid (`OnInvalidSubmit`) submissions.</span></span> <span data-ttu-id="dd7cc-121">また、検証を自分でトリガーして処理できる、より汎用的な `OnSubmit` イベントもあります。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-121">There's also a more generic `OnSubmit` event that lets you trigger and handle the validation yourself.</span></span>

<span data-ttu-id="dd7cc-122">検証エラーの概要を表示するには、`ValidationSummary` コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-122">To display a validation error summary, use the `ValidationSummary` component.</span></span> <span data-ttu-id="dd7cc-123">特定の入力フィールドの検証メッセージを表示するには、`ValidationMessage` コンポーネントを使用して、適切なモデルメンバーを指す `For` パラメーターにラムダ式を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-123">To display validation messages for a specific input field, use the `ValidationMessage` component, specifying a lambda expression for the `For` parameter that points to the appropriate model member.</span></span>

<span data-ttu-id="dd7cc-124">次の種類のモデルでは、データ注釈を使用して複数の検証規則を定義しています。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-124">The following model type defines several validation rules using data annotations:</span></span>

```csharp
using System;
using System.ComponentModel.DataAnnotations;

public class Starship
{
    [Required]
    [StringLength(16,
        ErrorMessage = "Identifier too long (16 character limit).")]
    public string Identifier { get; set; }

    public string Description { get; set; }

    [Required]
    public string Classification { get; set; }

    [Range(1, 100000,
        ErrorMessage = "Accommodation invalid (1-100000).")]
    public int MaximumAccommodation { get; set; }

    [Required]
    [Range(typeof(bool), "true", "true",
        ErrorMessage = "This form disallows unapproved ships.")]
    public bool IsValidatedDesign { get; set; }

    [Required]
    public DateTime ProductionDate { get; set; }
}
```

<span data-ttu-id="dd7cc-125">次のコンポーネントは、`Starship` モデルの種類に基づいて、Blazor でフォームを構築する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-125">The following component demonstrates building a form in Blazor based on the `Starship` model type:</span></span>

```razor
<h1>New Ship Entry Form</h1>

<EditForm Model="@starship" OnValidSubmit="@HandleValidSubmit">
    <DataAnnotationsValidator />
    <ValidationSummary />

    <p>
        <label for="identifier">Identifier: </label>
        <InputText id="identifier" @bind-Value="starship.Identifier" />
        <ValidationMessage For="() => starship.Identifier" />
    </p>
    <p>
        <label for="description">Description (optional): </label>
        <InputTextArea id="description" @bind-Value="starship.Description" />
    </p>
    <p>
        <label for="classification">Primary Classification: </label>
        <InputSelect id="classification" @bind-Value="starship.Classification">
            <option value="">Select classification ...</option>
            <option value="Exploration">Exploration</option>
            <option value="Diplomacy">Diplomacy</option>
            <option value="Defense">Defense</option>
        </InputSelect>
        <ValidationMessage For="() => starship.Classification" />
    </p>
    <p>
        <label for="accommodation">Maximum Accommodation: </label>
        <InputNumber id="accommodation" @bind-Value="starship.MaximumAccommodation" />
        <ValidationMessage For="() => starship.MaximumAccommodation" />
    </p>
    <p>
        <label for="valid">Engineering Approval: </label>
        <InputCheckbox id="valid" @bind-Value="starship.IsValidatedDesign" />
        <ValidationMessage For="() => starship.IsValidatedDesign" />
    </p>
    <p>
        <label for="productionDate">Production Date: </label>
        <InputDate id="productionDate" @bind-Value="starship.ProductionDate" />
        <ValidationMessage For="() => starship.ProductionDate" />
    </p>

    <button type="submit">Submit</button>
</EditForm>

@code {
    private Starship starship = new Starship();

    private void HandleValidSubmit()
    {
        // Save the data
    }
}
```

<span data-ttu-id="dd7cc-126">フォームの送信後、モデルバインドデータは、データベースのようなデータストアに保存されていません。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-126">After the form submission, the model-bound data hasn't been saved to any data store, like a database.</span></span> <span data-ttu-id="dd7cc-127">Blazor WebAssembly では、データをサーバーに送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-127">In a Blazor WebAssembly app, the data must be sent to the server.</span></span> <span data-ttu-id="dd7cc-128">たとえば、HTTP POST 要求を使用します。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-128">For example, using an HTTP POST request.</span></span> <span data-ttu-id="dd7cc-129">Blazor Server アプリでは、データは既にサーバー上に存在していますが、保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-129">In a Blazor Server app, the data is already on the server, but it must be persisted.</span></span> <span data-ttu-id="dd7cc-130">Blazor アプリでのデータアクセスの処理は、データの処理に[関する](data.md)セクションの対象です。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-130">Handling data access in Blazor apps is the subject of the [Dealing with data](data.md) section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dd7cc-131">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="dd7cc-131">Additional resources</span></span>

<span data-ttu-id="dd7cc-132">Blazor アプリでの[フォームと検証](/aspnet/core/blazor/forms-validation)の詳細については、Blazor のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd7cc-132">For more information on [forms and validation](/aspnet/core/blazor/forms-validation) in Blazor apps, see the Blazor documentation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="dd7cc-133">[前へ](state-management.md)
>[次へ](data.md)</span><span class="sxs-lookup"><span data-stu-id="dd7cc-133">[Previous](state-management.md)
[Next](data.md)</span></span>
