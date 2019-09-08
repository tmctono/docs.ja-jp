---
title: SetPEKind メソッド
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a48dbd38d357b668c2794ae6305ceb9cad3dcf4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787190"
---
# <a name="setpekind-method"></a><span data-ttu-id="4e3ac-102">SetPEKind メソッド</span><span class="sxs-lookup"><span data-stu-id="4e3ac-102">SetPEKind Method</span></span>
<span data-ttu-id="4e3ac-103">ポータブル実行可能ファイルの種類 (マシン固有またはコンピューターに依存しない) を決定します。</span><span class="sxs-lookup"><span data-stu-id="4e3ac-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e3ac-104">構文</span><span class="sxs-lookup"><span data-stu-id="4e3ac-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="4e3ac-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4e3ac-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="4e3ac-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="4e3ac-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="4e3ac-107">PE の種類を設定するファイルのトークン。</span><span class="sxs-lookup"><span data-stu-id="4e3ac-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="4e3ac-108">がバインドされ`AssemblyID`ていない .netmodule を示していない場合は、NULL にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4e3ac-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="4e3ac-109">[Corpekind 列挙体](../metadata/corpekind-enumeration.md)によって示される PE の種類。</span><span class="sxs-lookup"><span data-stu-id="4e3ac-109">The type of PE, as indicated by the [CorPEKind Enumeration](../metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="4e3ac-110">NT ヘッダーに示されている、対象コンピューターのアーキテクチャ。</span><span class="sxs-lookup"><span data-stu-id="4e3ac-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e3ac-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="4e3ac-111">Return Value</span></span>  
 <span data-ttu-id="4e3ac-112">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="4e3ac-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e3ac-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="4e3ac-113">Requirements</span></span>  
 <span data-ttu-id="4e3ac-114">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="4e3ac-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e3ac-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e3ac-115">See also</span></span>

- [<span data-ttu-id="4e3ac-116">GetPEKind メソッド</span><span class="sxs-lookup"><span data-stu-id="4e3ac-116">GetPEKind Method</span></span>](../metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="4e3ac-117">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4e3ac-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="4e3ac-118">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4e3ac-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="4e3ac-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="4e3ac-119">ALink API</span></span>](index.md)
