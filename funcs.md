Coords
type Scalar = Double
type XYPos = (Scalar, Scalar)   -- X-Y Position
type XYVec = (Scalar, Scalar)   -- X-Y Vector

midpoint (x1, y1) (x2,y2)
scaleVec x y (xs,ys)
sumPairs (two vectors, or point and vector)
sumVectors :: [ XYVec ]

sumVectorsWithDefault :: XYVec -> [ XYVec ] -> XYVec

sumVectorsWithDefault theDefault [] = theDefault
sumVectorsWithDefault theDefault vecs = sumVectors vecs

-- getStrings
--   Extracts the labels from a list of attributes
getStrings :: [Attribute] -> [String]

-- dirToVec
--   Turns a direction into a unit vector
dirToVec :: Direction -> XYVec

dirToVec Lt = (-1, 0)

-- attrsToVectors
--   Turns list of attributes into a list of vectors (numeric pairs),
--   ignoring labels.
--
--      E.g.,
--            attrsToVectors 2.0 3.0 [ Dir Up, "hi", Dir Lt]
--      becomes
--            [ (0,3.0), (-2.0,0) ]
--
--   The first two arguments are the default horizontal and vertical distances
--
attrsToVectors :: Scalar -> Scalar -> [Attribute] -> [ XYVec ]

