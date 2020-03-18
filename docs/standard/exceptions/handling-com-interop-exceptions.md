---
title: COM 相互運用の例外の処理
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- HRESULTs
- exceptions, COM interop
- COM interop, exceptions
ms.assetid: e6104aa8-8e5f-4069-b864-def85579c96c
ms.openlocfilehash: 17cd739ac40b43bdd4a93b83a4ab9d0d92400e2d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "75708933"
---
# <a name="handling-com-interop-exceptions"></a><span data-ttu-id="9a8c1-102">COM 相互運用の例外の処理</span><span class="sxs-lookup"><span data-stu-id="9a8c1-102">Handling COM Interop Exceptions</span></span>
<span data-ttu-id="9a8c1-103">マネージド コードとアンマネージド コードは、例外を処理するために一緒に操作できます。</span><span class="sxs-lookup"><span data-stu-id="9a8c1-103">Managed and unmanaged code can work together to handle exceptions.</span></span> <span data-ttu-id="9a8c1-104">マネージド コードでメソッドが例外をスローすると、共通言語ランタイムは、HRESULT を COM オブジェクトに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="9a8c1-104">If a method throws an exception in managed code, the common language runtime can pass an HRESULT to a COM object.</span></span> <span data-ttu-id="9a8c1-105">アンマネージド コードでメソッドが失敗して、失敗を示す HRESULT を返した場合、ランタイムはマネージド コードでキャッチできる例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="9a8c1-105">If a method fails in unmanaged code by returning a failure HRESULT, the runtime throws an exception that can be caught by managed code.</span></span>  
  
 <span data-ttu-id="9a8c1-106">ランタイムは、HRESULT を COM 相互運用からの自動的にマップして、より詳細な例外を取得します。</span><span class="sxs-lookup"><span data-stu-id="9a8c1-106">The runtime automatically maps the HRESULT from COM interop to more specific exceptions.</span></span> <span data-ttu-id="9a8c1-107">たとえば、E_ACCESSDENIED は <xref:System.UnauthorizedAccessException> になり、E_OUTOFMEMORY は <xref:System.OutOfMemoryException> になるなどです。</span><span class="sxs-lookup"><span data-stu-id="9a8c1-107">For example, E_ACCESSDENIED becomes <xref:System.UnauthorizedAccessException>, E_OUTOFMEMORY becomes <xref:System.OutOfMemoryException>, and so on.</span></span>  
  
 <span data-ttu-id="9a8c1-108">HRESULT がカスタムの結果であるか、またはランタイムで不明な場合は、ランタイムがジェネリック <xref:System.Runtime.InteropServices.COMException> をクライアントに渡します。</span><span class="sxs-lookup"><span data-stu-id="9a8c1-108">If the HRESULT is a custom result or if it is unknown to the runtime, the runtime passes a generic <xref:System.Runtime.InteropServices.COMException> to the client.</span></span> <span data-ttu-id="9a8c1-109">**COMException** の **ErrorCode** プロパティには、HRESULT 値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9a8c1-109">The **ErrorCode** property of the **COMException** contains the HRESULT value.</span></span>  
  
## <a name="working-with-ierrorinfo"></a><span data-ttu-id="9a8c1-110">IErrorInfo の処理</span><span class="sxs-lookup"><span data-stu-id="9a8c1-110">Working with IErrorInfo</span></span>  
 <span data-ttu-id="9a8c1-111">エラーが COM からマネージド コードに渡された場合、ランタイムは例外オブジェクトにエラー情報を入れます。</span><span class="sxs-lookup"><span data-stu-id="9a8c1-111">When an error is passed from COM to managed code, the runtime populates the exception object with error information.</span></span> <span data-ttu-id="9a8c1-112">IErrorInfo をサポートして HRESULT を返す COM オブジェクトは、この情報をマネージド コードの例外に提供します。</span><span class="sxs-lookup"><span data-stu-id="9a8c1-112">COM objects that support IErrorInfo and return HRESULTS provide this information to managed code exceptions.</span></span> <span data-ttu-id="9a8c1-113">たとえば、ランタイムは、COM エラーからの説明を例外の <xref:System.Exception.Message%2A> プロパティにマップします。</span><span class="sxs-lookup"><span data-stu-id="9a8c1-113">For example, the runtime maps the Description from the COM error to the exception's <xref:System.Exception.Message%2A> property.</span></span> <span data-ttu-id="9a8c1-114">HRESULT が追加のエラー情報を提供しない場合、ランタイムは例外のプロパティの多くに既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9a8c1-114">If the HRESULT provides no additional error information, the runtime fills many of the exception's properties with default values.</span></span>  
  
 <span data-ttu-id="9a8c1-115">アンマネージド コードでメソッドが失敗した場合、例外をマネージド コードのセグメントに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="9a8c1-115">If a method fails in unmanaged code, an exception can be passed to a managed code segment.</span></span> <span data-ttu-id="9a8c1-116">「[HRESULT と例外](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)」のトピックには、HRESULT がランタイム例外オブジェクトにマップする方法を示す表が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9a8c1-116">The topic [HRESULTS and Exceptions](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md) contains a table showing how HRESULTS map to runtime exception objects.</span></span>  

## <a name="see-also"></a><span data-ttu-id="9a8c1-117">参照</span><span class="sxs-lookup"><span data-stu-id="9a8c1-117">See also</span></span>

- [<span data-ttu-id="9a8c1-118">例外</span><span class="sxs-lookup"><span data-stu-id="9a8c1-118">Exceptions</span></span>](index.md)
