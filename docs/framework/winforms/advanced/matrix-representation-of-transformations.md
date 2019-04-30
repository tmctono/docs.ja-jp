---
title: 変換の行列表現
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- composite transformations
- transformations [Windows Forms], linear
- matrices
- translations in matrix representation
- transformations [Windows Forms], composite
- vectors
- linear transformations
- transformations [Windows Forms], matrix representation of
- transformations [Windows Forms], translation
- affine transformations
ms.assetid: 0659fe00-9e0c-41c4-9118-016f2404c905
ms.openlocfilehash: c87be8eaf715e373da75dd8f91889b0e396dba0d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967526"
---
# <a name="matrix-representation-of-transformations"></a><span data-ttu-id="3db44-102">変換の行列表現</span><span class="sxs-lookup"><span data-stu-id="3db44-102">Matrix Representation of Transformations</span></span>
<span data-ttu-id="3db44-103">M × n マトリックスは、一連の数値の m 行と n 個の列に配置します。</span><span class="sxs-lookup"><span data-stu-id="3db44-103">An m×n matrix is a set of numbers arranged in m rows and n columns.</span></span> <span data-ttu-id="3db44-104">次の図は、いくつかの行列を示します。</span><span class="sxs-lookup"><span data-stu-id="3db44-104">The following illustration shows several matrices.</span></span>  
  
 <span data-ttu-id="3db44-105">![Transformations](./media/aboutgdip05-art04.gif "AboutGdip05_art04")</span><span class="sxs-lookup"><span data-stu-id="3db44-105">![Transformations](./media/aboutgdip05-art04.gif "AboutGdip05_art04")</span></span>  
  
 <span data-ttu-id="3db44-106">同じサイズの 2 つの行列を追加するには、個々 の要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="3db44-106">You can add two matrices of the same size by adding individual elements.</span></span> <span data-ttu-id="3db44-107">次の図は、マトリックスの追加の 2 つの例を示します。</span><span class="sxs-lookup"><span data-stu-id="3db44-107">The following illustration shows two examples of matrix addition.</span></span>  
  
 <span data-ttu-id="3db44-108">![Transformations](./media/aboutgdip05-art05.gif "AboutGdip05_art05")</span><span class="sxs-lookup"><span data-stu-id="3db44-108">![Transformations](./media/aboutgdip05-art05.gif "AboutGdip05_art05")</span></span>  
  
 <span data-ttu-id="3db44-109">N × p マトリックスで m × n 行列を乗算でき、m × p 行列になります。</span><span class="sxs-lookup"><span data-stu-id="3db44-109">An m×n matrix can be multiplied by an n×p matrix, and the result is an m×p matrix.</span></span> <span data-ttu-id="3db44-110">最初のマトリックスの列の数は、2 番目の行列内の行の数と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3db44-110">The number of columns in the first matrix must be the same as the number of rows in the second matrix.</span></span> <span data-ttu-id="3db44-111">たとえば、4 × 2 マトリックスは、4 × 3 マトリックスを生成するために 2 × 3 行列を掛けることができます。</span><span class="sxs-lookup"><span data-stu-id="3db44-111">For example, a 4×2 matrix can be multiplied by a 2×3 matrix to produce a 4×3 matrix.</span></span>  
  
 <span data-ttu-id="3db44-112">平面と行と列の行列内のポイントは、ベクトルとして考えることができます。</span><span class="sxs-lookup"><span data-stu-id="3db44-112">Points in the plane and rows and columns of a matrix can be thought of as vectors.</span></span> <span data-ttu-id="3db44-113">たとえば、(2, 5) は、2 つのコンポーネントを持つベクトルと (3, 7, 1) は 3 つのコンポーネントを持つベクター。</span><span class="sxs-lookup"><span data-stu-id="3db44-113">For example, (2, 5) is a vector with two components, and (3, 7, 1) is a vector with three components.</span></span> <span data-ttu-id="3db44-114">2 つのベクトルのドット積の定義は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3db44-114">The dot product of two vectors is defined as follows:</span></span>  
  
 <span data-ttu-id="3db44-115">(a、b) • (c、d) = ac + bd</span><span class="sxs-lookup"><span data-stu-id="3db44-115">(a, b) • (c, d) = ac + bd</span></span>  
  
 <span data-ttu-id="3db44-116">(a、b、c) • (d、e、f) = ad + する + cf</span><span class="sxs-lookup"><span data-stu-id="3db44-116">(a, b, c) • (d, e, f) = ad + be + cf</span></span>  
  
 <span data-ttu-id="3db44-117">たとえば、ドット積 (2, 3) と (5, 4) は (2)(5) + (3)(4) = 22。</span><span class="sxs-lookup"><span data-stu-id="3db44-117">For example, the dot product of (2, 3) and (5, 4) is (2)(5) + (3)(4) = 22.</span></span> <span data-ttu-id="3db44-118">(2, 5, 1) のドット積と (4, 3, 1) は (2)(4) + (5)(3) + (1)(1) = 24。</span><span class="sxs-lookup"><span data-stu-id="3db44-118">The dot product of (2, 5, 1) and (4, 3, 1) is (2)(4) + (5)(3) + (1)(1) = 24.</span></span> <span data-ttu-id="3db44-119">2 つのベクトルのドット積が数、別のベクトルであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3db44-119">Note that the dot product of two vectors is a number, not another vector.</span></span> <span data-ttu-id="3db44-120">ドット積を計算できるは、2 つのベクトルのコンポーネントの数が同じ場合のみにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="3db44-120">Also note that you can calculate the dot product only if the two vectors have the same number of components.</span></span>  
  
 <span data-ttu-id="3db44-121">ように A(i, j) には、i 番目の行と、j 番目の列の行列 A のエントリがあります。</span><span class="sxs-lookup"><span data-stu-id="3db44-121">Let A(i, j) be the entry in matrix A in the ith row and the jth column.</span></span> <span data-ttu-id="3db44-122">たとえば、A (3, 2) は行列 A の 3 行目、2 番目の列内のエントリです。</span><span class="sxs-lookup"><span data-stu-id="3db44-122">For example A(3, 2) is the entry in matrix A in the 3rd row and the 2nd column.</span></span> <span data-ttu-id="3db44-123">A、B、および C、マトリックス、および AB と C. を =C のエントリは、次のように計算されます。</span><span class="sxs-lookup"><span data-stu-id="3db44-123">Suppose A, B, and C are matrices, and AB = C. The entries of C are calculated as follows:</span></span>  
  
 <span data-ttu-id="3db44-124">C (i, j) = (A の行 i) • (B の列 j)</span><span class="sxs-lookup"><span data-stu-id="3db44-124">C(i, j) = (row i of A) • (column j of B)</span></span>  
  
 <span data-ttu-id="3db44-125">次の図は、行列乗算のいくつかの例を示します。</span><span class="sxs-lookup"><span data-stu-id="3db44-125">The following illustration shows several examples of matrix multiplication.</span></span>  
  
 <span data-ttu-id="3db44-126">![Transformations](./media/aboutgdip05-art06.gif "AboutGdip05_art06")</span><span class="sxs-lookup"><span data-stu-id="3db44-126">![Transformations](./media/aboutgdip05-art06.gif "AboutGdip05_art06")</span></span>  
  
 <span data-ttu-id="3db44-127">1 × 2 マトリックス平面上のポイントの場合は、そのポイントを 2 × 2 の行列を乗算することによって変換できます。</span><span class="sxs-lookup"><span data-stu-id="3db44-127">If you think of a point in a plane as a 1×2 matrix, you can transform that point by multiplying it by a 2×2 matrix.</span></span> <span data-ttu-id="3db44-128">次の図は、点 (2, 1) に適用されるいくつかの変換を示します。</span><span class="sxs-lookup"><span data-stu-id="3db44-128">The following illustration shows several transformations applied to the point (2, 1).</span></span>  
  
 <span data-ttu-id="3db44-129">![Transformations](./media/aboutgdip05-art07.gif "AboutGdip05_art07")</span><span class="sxs-lookup"><span data-stu-id="3db44-129">![Transformations](./media/aboutgdip05-art07.gif "AboutGdip05_art07")</span></span>  
  
 <span data-ttu-id="3db44-130">上記の図に示すように変換のすべてが、線形変換します。</span><span class="sxs-lookup"><span data-stu-id="3db44-130">All of the transformations shown in the preceding figure are linear transformations.</span></span> <span data-ttu-id="3db44-131">変換など、他の特定の変換は線形的ではなくで 2 × 2 の行列の乗算では表現できません。</span><span class="sxs-lookup"><span data-stu-id="3db44-131">Certain other transformations, such as translation, are not linear, and cannot be expressed as multiplication by a 2×2 matrix.</span></span> <span data-ttu-id="3db44-132">たいとします最初に、点 (2, 1)、90 ° 回転して、3 ユニット x 方向に変換するためおよび y 方向の 4 つの単位に変換するためです。</span><span class="sxs-lookup"><span data-stu-id="3db44-132">Suppose you want to start with the point (2, 1), rotate it 90 degrees, translate it 3 units in the x direction, and translate it 4 units in the y direction.</span></span> <span data-ttu-id="3db44-133">マトリックスの追加後に、行列の乗算を使用して、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3db44-133">You can accomplish this by using a matrix multiplication followed by a matrix addition.</span></span>  
  
 <span data-ttu-id="3db44-134">![Transformations](./media/aboutgdip05-art08.gif "AboutGdip05_art08")</span><span class="sxs-lookup"><span data-stu-id="3db44-134">![Transformations](./media/aboutgdip05-art08.gif "AboutGdip05_art08")</span></span>  
  
 <span data-ttu-id="3db44-135">翻訳 (1 × 2 マトリックスの追加) 後に線形変換 (2 × 2 行列乗算) は、アフィン変換と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="3db44-135">A linear transformation (multiplication by a 2×2 matrix) followed by a translation (addition of a 1×2 matrix) is called an affine transformation.</span></span> <span data-ttu-id="3db44-136">マトリックス (線形の 1 つ)、および翻訳用に 1 つのペアでアフィン変換を格納する代わりにでは、3 × 3 行列で変換全体を格納します。</span><span class="sxs-lookup"><span data-stu-id="3db44-136">An alternative to storing an affine transformation in a pair of matrices (one for the linear part and one for the translation) is to store the entire transformation in a 3×3 matrix.</span></span> <span data-ttu-id="3db44-137">この作業を行うには、ダミーの 3 番目の座標で、1 × 3 マトリックスで平面のポイントを格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3db44-137">To make this work, a point in the plane must be stored in a 1×3 matrix with a dummy 3rd coordinate.</span></span> <span data-ttu-id="3db44-138">通常の手法は、すべての 3 番目の座標を 1 に等しいようにすることです。</span><span class="sxs-lookup"><span data-stu-id="3db44-138">The usual technique is to make all 3rd coordinates equal to 1.</span></span> <span data-ttu-id="3db44-139">たとえば、行列 [2 1 1] を使用して、ポイント (2, 1) が表されます。</span><span class="sxs-lookup"><span data-stu-id="3db44-139">For example, the point (2, 1) is represented by the matrix [2 1 1].</span></span> <span data-ttu-id="3db44-140">次の図は、アフィン変換 (90 度回転、平行移動 3 ユニット x 方向に、y 方向の 4 つの単位) で 1 つの 3 つ × 3 行列の乗算で表されます。</span><span class="sxs-lookup"><span data-stu-id="3db44-140">The following illustration shows an affine transformation (rotate 90 degrees; translate 3 units in the x direction, 4 units in the y direction) expressed as multiplication by a single 3×3 matrix.</span></span>  
  
 <span data-ttu-id="3db44-141">![Transformations](./media/aboutgdip05-art09.gif "AboutGdip05_art09")</span><span class="sxs-lookup"><span data-stu-id="3db44-141">![Transformations](./media/aboutgdip05-art09.gif "AboutGdip05_art09")</span></span>  
  
 <span data-ttu-id="3db44-142">前の例では、点 (2, 1) は、ポイント (2, 6) にマップされます。</span><span class="sxs-lookup"><span data-stu-id="3db44-142">In the preceding example, the point (2, 1) is mapped to the point (2, 6).</span></span> <span data-ttu-id="3db44-143">数値 0、0、1 を 3 つ × 3 行列の 3 番目の列が含まれているに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3db44-143">Note that the third column of the 3×3 matrix contains the numbers 0, 0, 1.</span></span> <span data-ttu-id="3db44-144">アフィン変換の 3 つ × 3 マトリックスの場合と常になります。</span><span class="sxs-lookup"><span data-stu-id="3db44-144">This will always be the case for the 3×3 matrix of an affine transformation.</span></span> <span data-ttu-id="3db44-145">重要な数値は、列 1 と 2 列に 6 桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="3db44-145">The important numbers are the six numbers in columns 1 and 2.</span></span> <span data-ttu-id="3db44-146">マトリックスの左上の 2 × 2 部分は、変換の線形の一部を表し、3 番目の行の最初の 2 つのエントリが、翻訳を表します。</span><span class="sxs-lookup"><span data-stu-id="3db44-146">The upper-left 2×2 portion of the matrix represents the linear part of the transformation, and the first two entries in the 3rd row represent the translation.</span></span>  
  
 <span data-ttu-id="3db44-147">![Transformations](./media/aboutgdip05-art10.gif "AboutGdip05_art10")</span><span class="sxs-lookup"><span data-stu-id="3db44-147">![Transformations](./media/aboutgdip05-art10.gif "AboutGdip05_art10")</span></span>  
  
 <span data-ttu-id="3db44-148">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]でアフィン変換を格納することができます、<xref:System.Drawing.Drawing2D.Matrix>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3db44-148">In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] you can store an affine transformation in a <xref:System.Drawing.Drawing2D.Matrix> object.</span></span> <span data-ttu-id="3db44-149">アフィン変換を表す行列の 3 番目の列は常にあるため (0, 0, 1) を構築するとき、最初の 2 つの列に 6 桁の数字のみを指定する、<xref:System.Drawing.Drawing2D.Matrix>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3db44-149">Because the third column of a matrix that represents an affine transformation is always (0, 0, 1), you specify only the six numbers in the first two columns when you construct a <xref:System.Drawing.Drawing2D.Matrix> object.</span></span> <span data-ttu-id="3db44-150">ステートメント`Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)`上記の図に示すように、マトリックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="3db44-150">The statement `Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)` constructs the matrix shown in the preceding figure.</span></span>  
  
## <a name="composite-transformations"></a><span data-ttu-id="3db44-151">複合変換</span><span class="sxs-lookup"><span data-stu-id="3db44-151">Composite Transformations</span></span>  
 <span data-ttu-id="3db44-152">複合変換とは、変換後にもう 1 つのシーケンスです。</span><span class="sxs-lookup"><span data-stu-id="3db44-152">A composite transformation is a sequence of transformations, one followed by the other.</span></span> <span data-ttu-id="3db44-153">マトリックスと、次の一覧で変換を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="3db44-153">Consider the matrices and transformations in the following list:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3db44-154">行列 A</span><span class="sxs-lookup"><span data-stu-id="3db44-154">Matrix A</span></span>|<span data-ttu-id="3db44-155">90 度回転します。</span><span class="sxs-lookup"><span data-stu-id="3db44-155">Rotate 90 degrees</span></span>|  
|<span data-ttu-id="3db44-156">行列 B</span><span class="sxs-lookup"><span data-stu-id="3db44-156">Matrix B</span></span>|<span data-ttu-id="3db44-157">X 方向に 2 倍でスケーリングします。</span><span class="sxs-lookup"><span data-stu-id="3db44-157">Scale by a factor of 2 in the x direction</span></span>|  
|<span data-ttu-id="3db44-158">マトリックス C</span><span class="sxs-lookup"><span data-stu-id="3db44-158">Matrix C</span></span>|<span data-ttu-id="3db44-159">Y 方向のユニット 3 つを変換します。</span><span class="sxs-lookup"><span data-stu-id="3db44-159">Translate 3 units in the y direction</span></span>|  
  
 <span data-ttu-id="3db44-160">ポイント (2, 1) でまず — マトリックス [2 1 1] によって表される、C、点 (2, 1) が行われる順序で 3 つの変換し、A、B、乗算。</span><span class="sxs-lookup"><span data-stu-id="3db44-160">If we start with the point (2, 1) — represented by the matrix [2 1 1] — and multiply by A, then B, then C, the point (2, 1) will undergo the three transformations in the order listed.</span></span>  
  
 <span data-ttu-id="3db44-161">[2 1 1]ABC = [-2 5 1]</span><span class="sxs-lookup"><span data-stu-id="3db44-161">[2 1 1]ABC = [-2 5 1]</span></span>  
  
 <span data-ttu-id="3db44-162">はなく 3 つの独立した行列に複合変換の 3 つの部分を格納するよりは、A を乗算できます複合変換全体を格納する 1 つの 3 つ × 3 行列を取得するには、まとめて、B、および C。</span><span class="sxs-lookup"><span data-stu-id="3db44-162">Rather than store the three parts of the composite transformation in three separate matrices, you can multiply A, B, and C together to get a single 3×3 matrix that stores the entire composite transformation.</span></span> <span data-ttu-id="3db44-163">たとえば、ABC D. を =D を掛けたポイントが A、B、C の乗算ポイントと同じ結果を提供し、</span><span class="sxs-lookup"><span data-stu-id="3db44-163">Suppose ABC = D. Then a point multiplied by D gives the same result as a point multiplied by A, then B, then C.</span></span>  
  
 <span data-ttu-id="3db44-164">[2 1 1]D = [-2 5 1]</span><span class="sxs-lookup"><span data-stu-id="3db44-164">[2 1 1]D = [-2 5 1]</span></span>  
  
 <span data-ttu-id="3db44-165">次の図は、A、B、C および D のマトリックス</span><span class="sxs-lookup"><span data-stu-id="3db44-165">The following illustration shows the matrices A, B, C, and D.</span></span>  
  
 <span data-ttu-id="3db44-166">![Transformations](./media/aboutgdip05-art12.gif "AboutGdip05_art12")</span><span class="sxs-lookup"><span data-stu-id="3db44-166">![Transformations](./media/aboutgdip05-art12.gif "AboutGdip05_art12")</span></span>  
  
 <span data-ttu-id="3db44-167">複合変換の行列は、個々 の変換行列を掛け合わせることで形成できますファクトは 1 つの任意のアフィン変換のシーケンスを格納できることを意味<xref:System.Drawing.Drawing2D.Matrix>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3db44-167">The fact that the matrix of a composite transformation can be formed by multiplying the individual transformation matrices means that any sequence of affine transformations can be stored in a single <xref:System.Drawing.Drawing2D.Matrix> object.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="3db44-168">複合変換の順序が重要です。</span><span class="sxs-lookup"><span data-stu-id="3db44-168">The order of a composite transformation is important.</span></span> <span data-ttu-id="3db44-169">一般に、回転、拡大縮小、変換が同じではありません、スケーリング、回転、順に変換します。</span><span class="sxs-lookup"><span data-stu-id="3db44-169">In general, rotate, then scale, then translate is not the same as scale, then rotate, then translate.</span></span> <span data-ttu-id="3db44-170">同様に、行列乗算の順序が重要です。</span><span class="sxs-lookup"><span data-stu-id="3db44-170">Similarly, the order of matrix multiplication is important.</span></span> <span data-ttu-id="3db44-171">一般に、ABC はバックアップと同じです。</span><span class="sxs-lookup"><span data-stu-id="3db44-171">In general, ABC is not the same as BAC.</span></span>  
  
 <span data-ttu-id="3db44-172"><xref:System.Drawing.Drawing2D.Matrix>クラスが複合変換を構築するためのいくつかのメソッドを提供します。 <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A>、 <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A>、 <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A>、 <xref:System.Drawing.Drawing2D.Matrix.Scale%2A>、 <xref:System.Drawing.Drawing2D.Matrix.Shear%2A>、および<xref:System.Drawing.Drawing2D.Matrix.Translate%2A>します。</span><span class="sxs-lookup"><span data-stu-id="3db44-172">The <xref:System.Drawing.Drawing2D.Matrix> class provides several methods for building a composite transformation: <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A>, <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A>, <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A>, <xref:System.Drawing.Drawing2D.Matrix.Scale%2A>, <xref:System.Drawing.Drawing2D.Matrix.Shear%2A>, and <xref:System.Drawing.Drawing2D.Matrix.Translate%2A>.</span></span> <span data-ttu-id="3db44-173">次の例では、30 ° 度回転し、y 方向の 2 倍で拡大または縮小し、x 方向に 5 つのユニットを変換する複合変換の行列を作成します。</span><span class="sxs-lookup"><span data-stu-id="3db44-173">The following example creates the matrix of a composite transformation that first rotates 30 degrees, then scales by a factor of 2 in the y direction, and then translates 5 units in the x direction:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.CoordinateSystems#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#11)]  
  
 <span data-ttu-id="3db44-174">次の図は、マトリックスを示します。</span><span class="sxs-lookup"><span data-stu-id="3db44-174">The following illustration shows the matrix.</span></span>  
  
 <span data-ttu-id="3db44-175">![Transformations](./media/aboutgdip05-art13.gif "AboutGdip05_art13")</span><span class="sxs-lookup"><span data-stu-id="3db44-175">![Transformations](./media/aboutgdip05-art13.gif "AboutGdip05_art13")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3db44-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="3db44-176">See also</span></span>

- [<span data-ttu-id="3db44-177">座標系と変換</span><span class="sxs-lookup"><span data-stu-id="3db44-177">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="3db44-178">マネージド GDI+ での変換の使用</span><span class="sxs-lookup"><span data-stu-id="3db44-178">Using Transformations in Managed GDI+</span></span>](using-transformations-in-managed-gdi.md)
